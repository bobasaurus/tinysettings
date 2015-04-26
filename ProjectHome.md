This is a small C++ library that enables persistent program settings, making use of the excellent [TinyXML](http://www.grinninglizard.com/tinyxml/) library.  Use this anywhere you want to create, modify, save, and load program configuration settings using a small xml file.  Example usage:


```
TinySettings settings;
//load in a settings file if it exists (otherwise, a new file of the given name will be created when settings are saved later)
settings.LoadXMLSettings("settings.xml");

//set a setting
settings["someName"] = "value";

//get a setting by its name (if it doesn't exist, this creates an empty setting and returns an empty string)
std::string settingStr = settings["someOtherName"];

//save any new or modified settings
settings.SaveXMLSettings();
```


Note that you will need to include and link the TinyXML STL libraries for this to work.  If you're still getting linker errors in Visual Studio, try setting the "C/C++ -> Code Generation -> Runtime Library" project property to "Multi-threaded (/MT)" or "Multi-threaded Debug (/MTd)", depending on your build configuration.