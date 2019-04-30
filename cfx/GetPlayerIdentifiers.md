---
ns: cfx
---
## GetPlayerIdentifiers
A variation of GetPlayerIdentifier that returns identifiers in table format.  Useful as it will get ALL identifiers available.

```lua
local retval --[[ table ]] =
	GetPlayerIdentifiers(
		srcPlayer --[[ int ]]
	)
```

```c
// Could be wrong
void GET_PLAYER_IDENTIFIERS(char* srcPlayer)
```

## Information & Usage
srcPlayer - The player from which to pull identifiers

Can be used inside PlayerConnecting event to grab all available identifiers on join.

## Example

```lua
    local steamid  = false
    local license  = false
    local discord  = false
    local xbl      = false
    local liveid   = false
    local ip       = false

  for k,v in pairs(GetPlayerIdentifiers(source))do
    print(v)
        
      if string.sub(v, 1, string.len("steam:")) == "steam:" then
        steamid = v
      elseif string.sub(v, 1, string.len("license:")) == "license:" then
        license = v
      elseif string.sub(v, 1, string.len("xbl:")) == "xbl:" then
        xbl  = v
      elseif string.sub(v, 1, string.len("ip:")) == "ip:" then
        ip = v
      elseif string.sub(v, 1, string.len("discord:")) == "discord:" then
        discord = v
      elseif string.sub(v, 1, string.len("live:")) == "live:" then
        liveid = v
      end
    
  end
```
