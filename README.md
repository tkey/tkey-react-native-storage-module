# tKey React Native Storage Module

[![npm version](https://img.shields.io/npm/v/@tkey/react-native-storage?label=%22%22)](https://www.npmjs.com/package/@tkey/react-native-storage/v/latest)                  [![minzip](https://img.shields.io/bundlephobia/minzip/@tkey/react-native-storage?label=%22%22)](https://bundlephobia.com/result?p=@tkey/react-native-storage@latest) 

The tKey React Native Storage Module helps you store and recall key shares in the react-native secure storage. This module is the part of the [tKey SDK](https://github.com/tkey/tkey/).

## Installation

```shell
npm install --save @tkey/react-native-storage
```

## Initialization

### Bare React Native

```tsx
import { ReactNativeStorageModule } from "@tkey/react-native-storage";
import EncryptedStorage from "react-native-encrypted-storage";
const reactNativeStorageModule = new ReactNativeStorageModule(EncryptedStorage);
```

### Expo React Native

```tsx
import { ReactNativeStorageModule } from "@tkey/react-native-storage";
import * as SecureStore from "expo-secure-store";
const reactNativeStorageModule = new ReactNativeStorageModule(SecureStore);
```

## Usage

### Get ShareStore from Storage

```tsx
const share = await(tKeyInstance.modules.reactNativeStorage as ReactNativeStorageModule).getStoreFromReactNativeStorage();
```

### Store Device Share

```tsx
const generateShareResult = await tKeyInstance.generateNewShare();
const share = await tKeyInstance.outputShareStore(generateShareResult.newShareIndex);
await(tKeyInstance.modules.reactNativeStorage as ReactNativeStorageModule).storeDeviceShare(share);
```

### See the full [SDK Reference](https://web3auth.io/docs/sdk/core-kit/tkey/modules/react-native-storage) on the Web3Auth Documentation
