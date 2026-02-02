all: jupython.sif  # additional .sif files may be listed here for corresponding dockerfiles

%.sif: dockerfiles/%/Dockerfile
	docker build -t $* -f dockerfiles/$*/Dockerfile . && \
	scripts/convert_docker_image_to_singularity.sh $* && \
	scripts/move_singularity_file.sh $*

# Example commands executed by this make file
# 
# Running "make jupython.sif" will issue the following commands:
# docker build -t jupython -f dockerfiles/jupython/Dockerfile . && \  # build docker container
#     scripts/convert_docker_image_to_singularity.sh jupython && \         # produces jupython.sif
#     scripts/move_singularity_file.sh.sh jupython        # moves jupython.sif to ../singularity/.
#  
# Running "make all" will build all singularity containers in this project
