Commands that need to be run on startup:
- modprobe snd-virmidi

Files that need to be changed:
settings.json
- audio.bufferSize = 1024
- midi.device = /dev/snd/midiC1D0
- instruments need to be in the proper layout for their device files to be found

Commands that need to be run in separate terminals:
- sudo jackd -r -m -dalsa -dhw:0 -r48000 -p1024 -n2 -P
- sudo open-nsynth-super/app/open-nsynth/bin/open-nsynth
- vmpk
	- Under edit->connections, enable MIDI thru on MIDI output and set the Output MIDI connection to Virtual Raw MIDI 1-0:0
- Instead of vmpk, use `aplaymidi` to play a midi file
