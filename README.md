# GMOD-ADRA-SYSTEM
게리모드 ADRA 관련 오픈소스 및 호스팅 프로젝트입니다.

# 구글 TTS 게리모드 루아 함수
```lua
function google_tts( text )
    text = string.gsub (text, "\n", "\r\n")
    text = string.gsub(text, "([^%w _ %- . ~])", function (c) return string.format ("%%%02X", string.byte(c)) end)
    text = string.gsub (text, " ", "+")
    sound.PlayURL ( "http://translate.google.com/translate_tts?ie=UTF-8&total=1&idx=0&textlen=32&client=tw-ob&tl=ko-kr&q=" .. text, "", function( station ) 
        if ( IsValid( station ) ) then 
            station:Play()
        end
    end )
end
```
