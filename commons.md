# Commons cmd

__How to get systeme infos ?__
    
    # Kernel Version?
    uname -a
    
    # Release infos
    lsb_release -a
    cat /etc/*-release
    

__How to check process/ports usage ?__

    netstat -taupen
    
    # Process of user toto
    top -U toto
    
    
__Add user to sudoers group__

    adduser -aG toto sudo
