**INTRO**

**Optcmd** is simple plugin, that allow you to call confirm() function 
for your own list of commands (btw, you can have as many lists as you need).
After choosing command it will be processed depend on current prefix parameter.

**INSTALLATION**

Install this plugin using vundle (https://github.com/VundleVim/Vundle.vim).

Just add to your **.vimrc** next lines:

**Plugin** 'sergio-ivanuzzo/optcmd'

Then run:

vim +PluginInstall +qall

**QUICK START**

To work with this plugin, do next:

    1) add to your .vimrc list of dictionaries like below:

    let commands = [
        \{'prefix': 'console', 'command': 'ls -al > file.txt', 'index': '1'},
        \{'prefix': 'function', 'command': 'somePluginFunction()', 'index': '2'},
        \{'prefix': 'command', 'command': 'vim_native_command', index: '3'}
        \]

    2) add greet message for confirm() :

    let message = "Choose command:"

    2) add keymap for call optcmd#ChooseCommand(message, commands) :

        nmap <C-k> :call optcmd#ChooseCommand(message, commands) <CR>

        you can have as many keymaps for this as you want

    Commands prefixes:
        a) 'console' run command in external shell
        b) 'function' run command as vim function (via :call)
        c) 'command' run command as simple vim command

    Index option uses as shortcut for confirm() (:help confirm() for more details).
    This option can bi omitted (so, as shortcut will be used first letter of command)
    

**ABOUT**

I hope, this plugin will be useful for you! If you have any questions, propositions etc,
please, contact me <sergio.ivanuzzo at gmail dot com>

I will be glad if you help me to improve this plugin!

