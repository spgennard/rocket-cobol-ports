EXE_EXT=
SO_EXT=.so
KECCAK_CBL=KECCAK.cob
KECCAK_O=STATE_PERMUTE.o KECCAK.o READ_LANE.o WRITE_LANE.o LFSR86540.o XOR_LANE.o ROL_LANE.o

all:	SHAKE128$(SO_EXT) SHAKE256$(SO_EXT) SHA3_224$(SO_EXT) \
        SHA3_256$(SO_EXT) SHA3_384$(SO_EXT) SHA3_512$(SO_EXT) KECCAK.o \
        TESTSHA3$(EXE_EXT) SHA3_512.o   SESSION_ID.o TEST_SESSION_ID$(EXE_EXT) \
        SHA3_256.o   SESSION_ID_256.o TEST_SESSION_ID_256$(EXE_EXT)

# SESSION_ID        cobc
TEST_SESSION_ID$(EXE_EXT):	TEST_SESSION_ID.cob
	cob -xU TEST_SESSION_ID.cob

SESSION_ID.o:	SESSION_ID.cob SHA3_512.o $(KECCAK_O)
	cob -z SESSION_ID.cob SHA3_512.o $(KECCAK_O)
    
SHA3_512.o:	SHA3_512.cob
	cob -vxc -vxc 'sourceformat(free)' SHA3_512.cob

# SESSION_ID_256
TEST_SESSION_ID_256$(EXE_EXT):	TEST_SESSION_ID_256.cob
	cob -xU TEST_SESSION_ID_256.cob

SESSION_ID_256.o:	SESSION_ID_256.cob SHA3_256.o $(KECCAK_O)
	cob -z SESSION_ID_256.cob SHA3_256.o $(KECCAK_O)
    
SHA3_256.o:	SHA3_256.cob
	cob -vxc -vxc 'sourceformat(free)' SHA3_256.cob
    
# SHA3    
TESTSHA3$(EXE_EXT):	TESTSHA3.cob
	cob -xU TESTSHA3.cob
    
SHAKE128$(SO_EXT):	SHAKE128.cob $(KECCAK_O)
	cob -z SHAKE128.cob $(KECCAK_O)
    
SHAKE256$(SO_EXT):	SHAKE256.cob $(KECCAK_O)
	cob -z SHAKE256.cob $(KECCAK_O)
    
SHA3_224$(SO_EXT):	SHA3_224.cob $(KECCAK_O)
	cob -z SHA3_224.cob $(KECCAK_O)

SHA3_256$(SO_EXT):	SHA3_256.cob $(KECCAK_O)
	cob -z SHA3_256.cob $(KECCAK_O)
    
SHA3_384$(SO_EXT):	SHA3_384.cob $(KECCAK_O)
	cob -z SHA3_384.cob $(KECCAK_O)
    
SHA3_512$(SO_EXT):	SHA3_512.cob $(KECCAK_O)
	cob -z SHA3_512.cob $(KECCAK_O)
    
KECCAK.o:	KECCAK.cob
	cob -vxc -vxc 'sourceformat(free)' KECCAK.cob

STATE_PERMUTE.o:	KECCAK.cob
	cob -vxc -vxc 'sourceformat(free)' KECCAK.cob

XOR_LANE.o:	KECCAK.cob
	cob -vxc -vxc 'sourceformat(free)' KECCAK.cob

ROL_LANE.o:	KECCAK.cob
	cob -vxc -vxc 'sourceformat(free)' KECCAK.cob

clean:
	rm -f KECCAK.o
	rm -f KECCAK$(SO_EXT)
	rm -f SHAKE128$(SO_EXT)
	rm -f SHAKE256$(SO_EXT)
	rm -f SHA3_224$(SO_EXT)
	rm -f SHA3_256$(SO_EXT)
	rm -f SHA3_384$(SO_EXT)
	rm -f SHA3_512$(SO_EXT)
	rm -f TESTSHA3$(EXE_EXT)
	rm -f SHA3_256.o
	rm -f SESSION_ID_256$(SO_EXT)
	rm -f TEST_SESSION_ID_256$(EXE_EXT)
	rm -f SHA3_512.o
	rm -f SESSION_ID$(SO_EXT)
	rm -f TEST_SESSION_ID$(EXE_EXT)
