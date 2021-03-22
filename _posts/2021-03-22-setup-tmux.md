### Benefits of using tmux
 * tmux lets you detach from and re-attach sessions, so that you can leave your terminal sessions running in the background and resume them later. This is very important for ```ssh```. Let's say I've connected to a server via ```ssh```. I may lose connection anytime. Thus all my session data will be lost. But in case of tmux, it will be running the session in the background to which I can reattach. So my session data will not be lost unless server restarted.
 * We can use ```tmux``` with ```vim```. It will help us open vertical, horizontal or completely new sessions in which I can use ```vim``` or any other processes. I can transition between sessions using keyboard only.

<iframe width="560" height="315" src="https://www.youtube.com/embed/Yl7NFenTgIo" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

### Usage
* Creating new session
```bash
$ tmux
```
![creating_new_session]({{site.url}}/{{site.baseurl}}/assets/tmux/creating_new_session.png)

---


* Vertical pane
```cntrl + b %```
![vertical_pane]({{site.url}}/{{site.baseurl}}/assets/tmux/vertical_pane.png)

---

* horizontal pane
```cntrl + b "``` 
![horizontal_pane]({{site.url}}/{{site.baseurl}}/assets/tmux/horizontal_pane.png)

---

* Pane transitions
```cntrl + b ◁``` or ```cntrl + b ▷``` or ```cntrl + △``` or ```cntrl + b ▽```

---

* Pane resize
If the previous keys are pressed simultaneously, pane will be resized

---

* Pane or window close
```bash
$ exit
```

---

* New window
```cntrl + b + c```
![new_window]({{site.url}}/{{site.baseurl}}/assets/tmux/new_window.png)

---

* Window transition
```cntrl + b + w```
![window_transition]({{site.url}}/{{site.baseurl}}/assets/tmux/window_transition.png)

---

* Window rename
```cntrl + b + ,```
![rename_window]({{site.url}}/{{site.baseurl}}/assets/tmux/rename_window.png)

---

* Detach Session
```cntrl + b + d```
![detach_session]({{site.url}}/{{site.baseurl}}/assets/tmux/detach_session.png)

* List current sessions
```bash
$ tmux ls
```
![list_sessions]({{site.url}}/{{site.baseurl}}/assets/tmux/list_sessions.png)

---

* Reattach session

```bash
$ tmux attach -t <session_number>
```

---

* Kill session

```bash
$ tmux kill-session -t <session_number>
```
![kill_session]({{site.url}}/{{site.baseurl}}/assets/tmux/kill_session.png)

***

## Summery

* Creating new session
```bash
$ tmux
```


* Vertical pane
```cntrl + b %```

* horizontal pane
```cntrl + b "``` 

* Pane transitions
```cntrl + b ◁``` or ```cntrl + b ▷``` or ```cntrl + △``` or ```cntrl + b ▽```


* Pane resize
If the previous keys are pressed simultaneously, pane will be resized


* Pane or window close
```bash
$ exit
```


* New window
```cntrl + b + c```


* Window transition
```cntrl + b + w```


* Window rename
```cntrl + b + ,```


* Detach Session
```cntrl + b + d```

* List current sessions
```bash
$ tmux ls
```

* Reattach session

```bash
$ tmux attach -t <session_number>
```


* Kill session

```bash
$ tmux kill-session -t <session_number>
```
