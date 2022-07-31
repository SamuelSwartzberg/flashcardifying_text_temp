# job control

job control is mainly performed by signals.
A job is a shell concept, but generally corresponds to a process group.
Jobs mainly exist to be siginalled by signals, all processes in a job are signalled at once.
`^Z` (as keyboard input)   Stop (not kill) the current program
the bg command takes a suspended command (e.g. one that was Ctrl-Z ed) and resumes its execution in the ⁑background⁑
fg  resume stopped task in foreground
bg  resume stopped task in background
⟮c+;＆⟯ at the ⟮end of an command⟯ ⟮puts it in the backround⟯ (but it ⟮still continues running⟯)
jobs|show processes running in the background
