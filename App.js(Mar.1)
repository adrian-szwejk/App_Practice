/*

import React from 'react';
import {Image, Platform, StyleSheet, Text, TouchableOpacity, View } from 'react-native'; 
import * as ImagePicker from 'expo-image-picker'
import * as Sharing from 'expo-sharing';
import uploadToAnonymousFilesAsync from 'anonymous-files'
*/
import 'react-native-gesture-handler';
import * as React from 'react';
import { Button, View, Text,} from 'react-native';
import { NavigationContainer } from '@react-navigation/native';
import { createStackNavigator } from '@react-navigation/stack';


function HomeScreen({ navigation }) {
  return (
    <View style={{ flex: 1, alignItems: 'center', justifyContent: 'center' }}>
      <Text>Home Screen</Text>
      <Button
        title="Go to Details"
        onPress={() => {
          /* 1. Navigate to the Details route with params */
          navigation.navigate('Details', {
            itemId: 86,
            otherParam: 'anything you want here',
          });
        }}
      />
    </View>
  );
}

function DetailsScreen({ route, navigation }) {
  /* 2. Get the param */
  const { itemId, otherParam } = route.params;
  return (
    <View style={{ flex: 1, alignItems: 'center', justifyContent: 'center' }}>
      <Text>Details Screen</Text>
      <Text>itemId: {JSON.stringify(itemId)}</Text>
      <Text>otherParam: {JSON.stringify(otherParam)}</Text>
      <Button
        title="Go to Details... again"
        onPress={() =>
          navigation.push('Details', {
            itemId: Math.floor(Math.random() * 100),
          })
        }
      />
      <Button title="Go to Home" onPress={() => navigation.navigate('Home')} />
      <Button title="Go back" onPress={() => navigation.goBack()} />
    </View>
  );
}

const Stack = createStackNavigator();

function App() {
  return (
    <NavigationContainer>
      <Stack.Navigator initialRouteName="Home">
        <Stack.Screen name="Home" component={HomeScreen} />
        <Stack.Screen name="Details" component={DetailsScreen} />
      </Stack.Navigator>
    </NavigationContainer>
  );
}
export default App;
/*
function code_app(){
  const [selectedImage, setSelectedImage] = React.useState(null);
      let openImagePickerAsync = async () => {
        let permissionResult = await ImagePicker.requestMediaLibraryPermissionsAsync();
        if (permissionResult.granted === false) {
          alert('Permission to access camera roll is required!');
          return;
        }
        let pickerResult = await ImagePicker.launchImageLibraryAsync();
        if (pickerResult.cancelled === true) {
          return;
        }
        if (Platform.OS === 'web') {
          let remoteUri = await uploadToAnonymousFilesAsync(pickerResult.uri);
          setSelectedImage({ localUri: pickerResult.uri, remoteUri });
        } else {
          setSelectedImage({ localUri: pickerResult.uri, remoteUri: null });
        } 
      };
      let openShareDialogAsync = async () => {
        if (!(await Sharing.isAvailableAsync())) {
          alert(`The image is available for sharing at: ${selectedImage.remoteUri}`);
          return;
        }
        await Sharing.shareAsync(selectedImage.localUri);
      }; 
      if (selectedImage !== null) {
        return (
          <View style={styles.container}>
            <Image source={{ uri: selectedImage.localUri }} style={styles.thumbnail} />
            <TouchableOpacity onPress={openShareDialogAsync} style={styles.button}>
              <Text style={styles.buttonText}>Share this photo</Text>
            </TouchableOpacity>
            </View>
        );
      }
      return (
        <View style={styles.container}>
          <Image source={{ uri: 'https://i.imgur.com/TkIrScD.png' }} style={styles.logo} />
          <Text style={styles.instructions}>
            To share a photo from your phone with a friend, just press the button below!
          </Text>
          <TouchableOpacity onPress={openImagePickerAsync} style={styles.button}>
            <Text style={styles.buttonText}>Pick a photo</Text>
          </TouchableOpacity>
        </View>
      );
}

const styles = StyleSheet.create({
  container: {
    flex: 1,
    backgroundColor: '#fff',
    alignItems: 'center',
    justifyContent: 'center',
  },
  logo: {
    width: 305,
    height: 159,
    marginBottom: 10,
  },
  instructions: {
    color: '#888',
    fontSize: 18,
    marginHorizontal: 15,
  }, 
  button: {
    backgroundColor: "blue",
    padding: 20,
    borderRadius: 5,
  },
  buttonText: {
    fontSize: 20,
    color: '#fff',
  }, 
  thumbnail: {
    width: 300,
    height: 300,
    resizeMode: "contain"
  },
});
*/
