Bootstrap: docker
From: humanlongevity/hla:0.0.0

##############################
# main
##############################

%post
    apt update
    apt install -y bc

    cd /opt/data/chr6
    wget https://github.com/humanlongevity/HLA/raw/34221ea2bb3e09177e237b33ba946404214cc270/data/chr6/hg38.chr6.fna.bwt -O hg38.chr6.fna.bwt

    cd /opt/bin
    wget https://raw.githubusercontent.com/humanlongevity/HLA/34221ea2bb3e09177e237b33ba946404214cc270/bin/get-reads-alt-unmap.sh -O get-reads-alt-unmap.sh

%runscript
    exec "python" "/opt/bin/run.py" "$@"

##############################
# foo
##############################

%apprun get-reads-alt-unmap
    exec "bash" "/opt/bin/get-reads-alt-unmap.sh" "$@"
