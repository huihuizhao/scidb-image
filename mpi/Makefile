CFLAGS = -O3 -L/usr/X11R6/lib -lm -lpthread -lX11 -lXext -fopenmp 
MPICC = mpicc.mpich2
MPICPP = mpic++.mpich
MPIRUN = mpirun.mpich

NP = -np 2
TEST_DIR = /home/suhailr/Downloads/1080p


mpitest:
	$(MPICC) $(CFLAGS) -o bin/mpitest src/test/mpi_test.c
	
imgavg:
	$(MPICPP) $(CFLAGS) -o bin/img_avg_mpi src/util/utils.c src/img_avg/img_avg_mpi.cpp 

runtest: imgavg
	$(MPIRUN) $(NP) bin/img_avg_mpi $(TEST_DIR)

all: mpitest runtest

clean:
	rm -f mpitest