- upgrade bash on windows
  
  ```bash
    lxrun /uninstall
    lxrun /install
  ```

  This works for minor update:

  ```dos
    sudo do-release-upgrade
  ```
- Set up username and password
- Ser up VcXsrv as X server and xfce4-terminal
  ```sudo apt-get install xfce4-terminal```
  - add to .bashrc
  ```
  export DISPLAY="localhost:0"
  export TERM=xterm-256color
  ```
  - fix dbus
  ```
  sudo sed -i 's$<listen>.*</listen>$<listen>tcp:host=localhost,port=0</listen>$' /etc/dbus-1/session.conf
  ```
  - create windows shortcut
  ```
  powershell -windowstyle hidden -Command "iex \"bash ~ -c 'DISPLAY=:0 xfce4-terminal'\" "
  ```
