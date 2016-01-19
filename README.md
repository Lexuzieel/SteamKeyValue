# Steam Key Value library
This is a C# library with key value class originating from [SteamKit](https://github.com/SteamRE/SteamKit) by Ryan Stecker & SteamRE Team.
Library gives ability to read more exotic type of key value files - Steam resource files.
### [Download latest compiled library here](https://github.com/Lexuzieel/SteamKeyValue/releases)
It features enhanced indexer with support for key duplicates:
```
KeyValue kv = KeyValue.LoadFromFile("path/to/kv/file");
---
file
{
  section
  {
    "key" "value1"
    "key" "value2"
  }
  case [$OSX]
  {
    "key" "value"
  }
}
---
Enhanced indexers:
  kv["section"]["key", 1].Value // value2
  kv["section"]["key", 0].Value = kv["section"]["key"].Value // value1
Conditionals reading:
  kv["case"].Condition // [$OSX]
```
