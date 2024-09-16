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
  <summary markdown=1> <s>'better' typer</s> &nbsp;upd: <a href='https://github.com/BrianPugh/cyclopts'>cyclopts</a> only misses autosuggestion to solve this </summary>
  
  Tiangolo's [typer](https://github.com/tiangolo/typer) originally made a number of things right - hierarchy of typers, strict type checking, 
  and auto-completion for a number of shells out-of-the-box.

  That said, typer lacks attention from tiangolo, and lost some critical parts of experience:
  - it is slow (500ms for auto suggestion is harsh)
  - way many dependencies 
  - does not handle async functions (fixable)
  - it is quite shell-y and not pythonic. I'd like to just call function from shell after all
    - strange rules for lists and *args (e.g. can't pass an empty list)
    - `func(*, kw_only_param, kw_param=False)` is not recognized
    - `func(param1, param2=None)` forces to use --param2=val instead of `call param1_val param2_val`
    - ~~`type | None` not supported~~ (fixed recently)
    - dataclasses / pydantic as inputs are not supported
  - 'just give me raw input, I'll put it to other bash command' is not supported

  That's my complains, but walk over [bugtracker](https://github.com/tiangolo/typer/issues) of typer to see what's in demand.

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

  While (unmerged) patches are available to support UDS in openssh, I'm on the market for something next-gen, 
  e.g. something like [SSH3](https://github.com/francoismichel/ssh3) + serving/connecting to unix sockets.
  
</details>


<details markdown=1>
  <summary markdown=1> <s>no-std rust barcode scanner </s> <a href='https://github.com/rxing-core/rxing'>rxing</a> solved it </summary>
  At some point I've been looking for a barcode scanner that I could embed in web page via WASM, 
  and from python too.

  Nothing was available at that point, but @hschimke kindly added support of WASM target and CLI to his rust project,
  and I recommend giving it a try. I could use it on different cell phones right from web page.
  
</details>


Remarks related to all project above

<details markdown=1>
  <summary> What exactly I am ready to help with (details) </summary>
  
  If you think taking one of these projects, I am happy to test your solution, provide detailed user feedback, maybe test in prodiction, and if it works, cover it here or in my blog.
  (or einops docs if it is relevant to einops).

  Note that doesn't include development, but programming is something enjoyable, <br />
  while finding someone interested in using your work is usually non-trivial 🙂.
  
</details>



