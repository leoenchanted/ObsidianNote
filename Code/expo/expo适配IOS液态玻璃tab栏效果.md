```javascript
import { Tabs } from "expo-router";
import React from "react";
import CustomTabBar from "../../src/components/CustomTabBar";
import { Platform } from "react-native";
import { NativeTabs, Icon, Label } from "expo-router/unstable-native-tabs";
export default function TabLayout() {
  if (Platform.OS === "ios") {
    return (
      <NativeTabs>
        <NativeTabs.Trigger name="index">
          <Label>首页</Label>
          <Icon sf={{ default: "house", selected: "house.fill" }}></Icon>

        </NativeTabs.Trigger>

        <NativeTabs.Trigger name="vibewall">

          <Label>VibeWall</Label>

          <Icon sf={{ default: "photo" }}></Icon>

        </NativeTabs.Trigger>

        <NativeTabs.Trigger name="tools">

          <Label>工具</Label>

          <Icon sf={{ default: "ruler" }}></Icon>

        </NativeTabs.Trigger>

        <NativeTabs.Trigger name="settings">

          <Label>设置</Label>

          <Icon sf={{ default: "gear" }}></Icon>

        </NativeTabs.Trigger>

      </NativeTabs>

    );

  }
  return (
    <Tabs
      tabBar={(props) => <CustomTabBar {...props} />}
      screenOptions={{
        headerShown: false,
        tabBarStyle: {
          backgroundColor: "transparent",
          elevation: 0,
          borderTopWidth: 0,
        },
      }}
    >
      <Tabs.Screen name="index" options={{ title: "Home" }} />
      <Tabs.Screen name="vibewall" options={{ title: "VibeWall" }} />
      <Tabs.Screen name="tools" options={{ title: "Tools" }} />
      <Tabs.Screen name="settings" options={{ title: "Settings" }} />
    </Tabs>
  );
}
```