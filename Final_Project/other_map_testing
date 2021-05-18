

import React, { useState, useEffect } from 'react';
import { Platform, Text, View, StyleSheet,Dimensions } from 'react-native';
import Constants from 'expo-constants'; 
import * as Location from 'expo-location';
import MapView from 'react-native-maps';
import { Marker } from "react-native-maps";

export default function App() {
  const [location, setLocation] = useState({
    latitude: 51.5078788,
    longitude: -0.0877321,
    latitudeDelta: 0.005,
    longitudeDelta: 0.005
  });
  const [errorMsg, setErrorMsg] = useState(null);

  useEffect(() => {
    (async () => {
      if (Platform.OS === 'android' && !Constants.isDevice) {
        setErrorMsg(
          'Oops, this will not work on Snack in an Android emulator. Try it on your device!'
        );
        return;
      }
      let { status } = await Location.requestForegroundPermissionsAsync();
      if (status !== 'granted') {
        setErrorMsg('Permission to access location was denied');
        return;
      }

      let location = await Location.getCurrentPositionAsync({});
      setLocation(location);
    })();
  }, []);

  let text = 'Waiting..';
  if (errorMsg) {
    text = errorMsg;
  } else if (location) {
    text = JSON.stringify(location);
  }
  

  var arr = new Array();
  arr=text.split(",");
  var dict={};
  for(var x=0; x<arr.length;x++){
    var arrs = new Array();
    arrs=arr[x].split(":");
    dict[arrs[0]]=arrs[1]
  }
  var lat=parseFloat(dict['"latitude"'])
  var lng=parseFloat(dict['"longitude"'])
  var lati=parseFloat(42.2635296)
  var long=parseFloat(-87.9809898)
  var truth
  if(parseFloat(lati.toFixed(5))==parseFloat(lat.toFixed(5))){
    truth=true
    lati=parseFloat(lat.toFixed(5))
  }
  else{
    truth =false
    
  }
  if(parseFloat(long.toFixed(5))==parseFloat(lng.toFixed(5))){
    truth=true
    long=parseFloat(lng.toFixed(5))
  }
  else{
    truth =false
    
  }
  return (
    <View style={mapstyles.container}>
      <MapView
        style={mapstyles.map} 
        showsUserLocation={true} 
        followsUserLocation={true} 
        showsCompass={true} 
        provider={Mapview.PROVIDER_GOOGLE} 
        initialRegion={{latitude:Number(lati),longitude:Number(long),latitudeDelta: 0.005,longitudeDelta: 0.005}}
      >
        <Marker pinColor= 'blue' coordinate= {{latitude:42.2635296,longitude:-87.9809898,latitudeDelta: 0.005,longitudeDelta: 0.005}} key={0} title={'Home'} description={'Where I live'} />
        <Marker pinColor= 'red' coordinate= {{latitude:42.2272,longitude:-87.9495,latitudeDelta: 0.005,longitudeDelta: 0.005}} key={1} title={'School'} description={'Where I learn'} />
        <Marker pinColor= 'green' coordinate= {{latitude:42.2139721,longitude:-87.932254,latitudeDelta: 0.005,longitudeDelta: 0.005}} key={2} title={'Half Day Forest Preserve'} description={'Where I run'} />
      </MapView>
    </View>
  );
}

//<Marker style={mapstyles.map} coordinate={{latitude:Number(lati),longitude:Number(long),latitudeDelta: 0.005,longitudeDelta: 0.005}} title="My Marker" description="Some description" pinColor="blue"/>
//<MapView style={mapstyles.map} initialRegion={{latitude:41.8781,longitude:-87.6298,latitudeDelta: 0.005,longitudeDelta: 0.005}}/>
//<MapView style={mapstyles.map} initialRegion={{latitude:Number(lati),longitude:Number(long),latitudeDelta: 0.005,longitudeDelta: 0.005}}/>
//<Text style={styles.paragraph}>{"It is "+lat+"\nNot "+lati+"\nIt is "+lng+"\nNot "+long+"\nThey are "+truth}</Text>

const styles = StyleSheet.create({
  container: {
    flex: 1,
    alignItems: 'center',
    justifyContent: 'center',
    padding: 20,
  },
  paragraph: {
    fontSize: 18,
    textAlign: 'center',
  },
});
const mapstyles = StyleSheet.create({
  container: {
    flex: 1,
    backgroundColor: '#fff',
    alignItems: 'center',
    justifyContent: 'center',
  },
  map: {
    width: Dimensions.get('window').width,
    height: Dimensions.get('window').height,
  },
});
