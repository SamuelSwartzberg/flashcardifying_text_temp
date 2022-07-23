# subtitles

WebVTT|Web Video Text Tracks Formats
⟮WebVTT⟯ and ⟮.srt⟯ are file formats for ⟮subtitles⟯. 
⟮WebVTT⟯ is ⟮based on⟯ and ⟮similar to⟯ ⟮.srt⟯ 
⟮.srt⟯ is ⟮more common⟯ than ⟮WebVTT⟯, but ⟮WebVTT⟯ is ⟮more new/featurefu⟯l. 
⟮Youtube⟯ amongst others does not support ⟮srt or WebVTT tag formatting⟯, and ⟮pretty much nothing⟯ supports ⟮most of WebVTT's most advanced features⟯. 
⟮WebVTT and .srt⟯ mark up their payload with ⟮HTML/XML-style tags⟯. 
Things in ⟮WebVTT/.srt⟯ are ⟮generally separated⟯ by ⟮a blank line (i.e. two newlines⟯) 

WebVTT delimits ⟮major sections⟯ with ⟮allcaps words⟯: 
section name|section semantics/function
⟮WEBVTT⟯|⟮c+;s32;Begin WebVTT document⟯ ⟮h2;(may be followed by ⟮text header on the same line⟯⟯)
⟮STYLE⟯|⟮inline styling section⟯
⟮NOTE⟯|⟮comment⟯



A ⟮cue⟯ is ⟮the main unit of information⟯ in ⟮WebVTT/.srt.⟯ 
⟮A cue⟯ ⟮starts (.srt)/may start (WebVTT⟯) with ⟮a header line⟯. 
⟮The header line that starts a cue⟯ must be ⟮a running number indicator⟯ in ⟮.srt⟯, this is ⟮optional⟯ in ⟮WebVTT⟯ 
⟮The line after the header line if it exists or the first line of a WebVTT/.srt⟯ ⟮cue⟯ contains ⟮the time to show the text⟯, consisting of ⟮two timestamps (RFC 3339 (hh):mm:ss.ttt⟯) ⟮c+;separated by ` → ` (notice the spaces).⟯⟮c+; Every line of a cue after the line specifying the time⟯ specifies ⟮text to be shown.⟯ Together, these are known as ⟮the payload⟯. 
Every line of a cue may optionally be ⟮started by `- `⟯, this will ⟮not be displayed⟯ 


WebVTT-specific properties


CSS property syntax|CSS function
⟮c+;vertical:rl/lr make captions go from top to bottom and either right → left or left → right (changes the direction of other settings by 90 deg⟯)
⟮line:0-100%⟯|⟮display the cue at % offset from the top (or left/right if vertical is specified) (i.e., along the y axis if no `vertical`⟯)
⟮position:0-100%⟯|⟮display the cue at % offset from the left (or top/bottom if vertical is specified) (i.e., along the x axis if no `vertical`⟯)
⟮size:0-100%⟯|⟮set the width of the cue to %⟯
⟮‹c.foo›content‹/c›⟯|⟮specify a class foo to target⟯
⟮‹ruby›...⟯|⟮add furigana etc.⟯
⟮‹v foo›⟯|⟮indicate that foo is speaking⟯
⟮align:start/end...⟯|⟮align the captions along the x-axis (if not `vertical`), i.e. the same axis as the position property⟯
⟮c+;‹font color="...⟯|⟮Set the text to a certain color⟯
⟮‹b›, ‹i›, ‹u›⟯|⟮make the text bold, italic or underlined⟯


WebVTT-specific selectors

CSS Selector|Selects
⟮::cue(.foo⟯)|⟮Target a cue with class foo (‹c.foo›⟯)
⟮::cue⟯|⟮Target any WebVTT cue (shown subtitle⟯)
⟮::cue(b⟯)|⟮Target a ‹b› tag within WebVTT⟯

If you ⟮specify timestamp text (WebVTT only⟯), then ⟮any text before a timestamp text whose time you are at or after⟯ is ⟮previous text⟯, ⟮the text from the current to the next timestamp tag⟯ is ⟮active text⟯ and ⟮text after the next timestamp tag⟯ is ⟮future text⟯. 
If we specify ⟮‹track kind="chapters"›⟯, cues ⟮may not overlap time-wise⟯, and payloads ⟮may not contain tags⟯ 
