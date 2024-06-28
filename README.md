### Hi-hello 👋

I enjoy working on really challenging scientific questions that will make a long-term difference. 

My current focus is ML + Bio (more specifically, protein design), but previously I developed a bunch of ML methods for CERN.

You can find my development/ML projects here on github: first of all, check `einops` (unless you already use it 😏).


### Projects I'm interested in

Are you looking for a programming project? I have some ideas for you:


<details markdown=1>
  <summary> einops support in ruff </summary>
  
  Einops is very readable per se, and mistakes are generally easy to detect, but how about making it even simpler with static analysis? 

  Some examples where it could be useful
  
  ```python
  rearrange(x, 'b h w c -> b (h w)') # complain on missing c
  rearrange(x, 'b h w 3 -> b (h w) 3') # anonymous axes like 3 are not available in rearrange
  rearrange(x, 'b (h w) c -> b h w c') # complain that either h or w should be provided
  ```
</details>

<details markdown=1>
  <summary> einops coloring in vs code </summary>
  
  Wouldn't it be great if reduced or added dimension was immediately colored? Something like:
  
  <img width="450" alt="Screenshot 2024-06-28 at 13 59 28" src="https://github.com/arogozhnikov/arogozhnikov/assets/6318811/2c6a63d7-2300-4f6d-8262-4768fcdc8816">

</details>


<details markdown=1>
  <summary> unix sockets in SSH-over-HTTP </summary>

  Do you use SSH? I guess you do, since you're on github.

  I've been using unix sockets (UDS) as endpoints for containers for a while now, and it (mostly) rocks.
  
  Several similar containers can live on the same instance, and each mounts a folder with UDS (multiple services usually).
  Domain sockets can provide access to various web-servers, and almost anything can serve from UDS.
  
  (If you use TCP port forwarding for containers, try using UDS, you may like it much better, specially if you manage many endpoints or containers!
  No security issues, and you can easily add/remove sockets on the fly and without port clashes! 
  Spice with using symlinks for synonyms, and network management stops being ugly.)

  Back to the point: openssh-server does not support serving on unix socket, so I use ugly hack with `socat` redirecting request to TCP port.
  Openssh-client does not support connecting to domain socket (easy to fix this in config though).

  While patches are available to support ssh sockets, I'm on the marker for something newer, e.g. something like 
  [SSH3](https://github.com/francoismichel/ssh3) + serving/connecting to unix sockets.
  
</details>


Remarks related to all project above

<details markdown=1>
  <summary> What exactly I am ready to help with (details) </summary>
  
  If you think taking one of these projects, I am ready to try your solution, provide user feedback, and if I like it, cover it here or in my blog.
  (or einops docs if it is relevant to einops).

  Note that doesn't include development, but programming is something enjoyable, 
  while finding someone interested in using your work is usually non-trivial.
  
</details>



