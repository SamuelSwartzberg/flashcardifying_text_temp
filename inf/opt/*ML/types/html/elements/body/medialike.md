# medialike

## media

### elements

‹video› and ‹audio› embed a video/audio media player.

### interface

Both HTMLVideoElement and HTMLAudioElement inherit from HTMLMediaElement.

### attributes

⟮muted⟯|⟮audio is muted/mute audio⟯|IDL ＆ Content
⟮paused⟯|⟮is paused/pause⟯|IDL
⟮loop⟯|⟮will loop/loop⟯|IDL ＆ Content
⟮controls⟯|⟮is showing controls/show controls⟯|IDL ＆ Content
⟮autoplay⟯|⟮will autoplay/enable autoplay⟯|IDL ＆ Content
⟮ended⟯|⟮Indicates whether it has finished playing⟯|IDL
⟮playbackRate⟯|⟮Represents the speed at which the thing is playing⟯|IDL

### events

#### attribute change

paused=false → paused=true|pause
paused=true → paused=false|play

### sources

You may define a single source for ‹video› or ‹audio› via a src element.
You may define multiple sources for ‹video› or ‹audio› via child ‹source› elements.
‹track› defines text tracks for media elements (‹video› and ‹audio›)

### poster

the poster attribute for video specifies a URL for an image to be shown while the video is downloading. 
If the poster attribute for ‹video› isn't specified, nothing is displayed until the first frame is available, then the first frame is shown as the poster frame.

### track

‹track› provides some kind of text track for a media element.
‹track› can ba a child of ‹video› or‹audio›

#### attributes

track has a default attribute to indicate that this is a default track
track has a kind attribute to indicate its purpose
track kinds: captions, chapters, descriptions, metadata, subtitles

## images

### img

‹img› is the HTML element used for including images

### picture

The ‹picture› element is an element for containing different versions of the same image.
The picture element contains 0 - ∞ source elements and one ‹img› element.
The ‹img› child of ‹picture› is there to act as a fallback and to give the picture its dimensions.

### srcset 

srcset-values ::=  ‹srcset-specifier›{, ‹srcset-specifier›}
srcset-specifier ::= ‹url› ‹integer›w
sizes-values ::= ‹sizes-specifier›{, ‹sizes-specifier›}
sizes-specifier ::= ‹media-query› ‹resolution-length-percentage›

scrset specifies a list of sources and their actual sizes, while sizes declares a set of media condition and what width the slot is presumed to be in that case (width as in resolution, not width of the  box). 
Using srcset, browser then picks the image whose width is closest to the slot width, but preferring ones that are too large than too small.
If no sizes is provided, the browser presumes the slot width is 100vw.

## source

the ‹source› element provides a single source for certain media elements.
The ‹source› element may be a child of ‹picture›, ‹video› and ‹audio›.
the type (a MIME type) of a ‹source› element is specified via the type attribute, or else the browser will check the MIME type in the HTTP header.
A  ‹source› element is associated with one or more conditions.
The conditions of a  ‹source› element are its `type` plus a media query specified in `media` if present.
A lists of ‹source›s represents a priority hierarchy - the browser will take the first one that matches all conditions.
‹source› elements for audio/video take their URL in a src attribute; ‹source› elements for picture take their URL in a srcset attribute