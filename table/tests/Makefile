

TerarkDir=/newssd1/temp/terark/src
TerarkLib=/newssd1/temp/terark-zip-rocksdb/pkg/terark-zip-rocksdb-Linux-x86_64-g++-4.8-bmi2-0
RocksDir=/newssd1/temp/rocksdb
CXX=g++
CFLAGS=-g3 -std=c++11 -fPIC -DINDEX_UT
#CFLAGS=-g -std=c++11 -ftest-coverage -fprofile-arcs
INC=-I. -I.. -I$(TerarkDir) -I$(RocksDir)/include -I$(RocksDir)
LIBPATH=-L. -L.. -L$(TerarkLib)/lib #-L$(RocksDir)
#LIB=-lpthread -lrocksdb -lterark-core-g++-4.8-d -lterark-fsa-g++-4.8-d -lterark-zbs-g++-4.8-d -lgcov
LIB=-lpthread -lterark-core-g++-4.8-d -lterark-fsa-g++-4.8-d -lterark-zbs-g++-4.8-d
OBJS=composite_sorteduint_ut.o composite_uint_ut.o composite_str_ut.o terark_zip_common.o terark_zip_index.o


all: test_composite
#all: test_full

test_composite: ${OBJS}
	${CXX} -g3 -std=c++11 ${INC} ${LIBPATH} -o index_composite_ut index_composite_ut.cc ${OBJS} ${LIB}
#	${CXX} -g3 -std=c++11 -ftest-coverage -fprofile-arcs ${INC} ${LIBPATH} -o index_composite_ut index_composite_ut.cc ${OBJS} ${LIB}

test_full: ${OBJS}
	${CXX} -g3 -std=c++11 ${INC} ${LIBPATH} -o index_full_ut index_full_ut.cc ${OBJS} ${LIB}

composite_sorteduint_ut.o:
	${CXX} ${CFLAGS} ${INC} ${LIBPATH} -c composite_sorteduint_ut.cc ${LIB}

composite_uint_ut.o:
	${CXX} ${CFLAGS} ${INC} ${LIBPATH} -c composite_uint_ut.cc ${LIB}

composite_str_ut.o:
	${CXX} ${CFLAGS} ${INC} ${LIBPATH} -c composite_str_ut.cc ${LIB}

terark_zip_common.o:
	${CXX} ${CFLAGS} -Wall ${INC} ${LIBPATH} -c ../terark_zip_common.cc ${LIB}

terark_zip_index.o:
	${CXX} ${CFLAGS} -Wall ${INC} ${LIBPATH} -c ../terark_zip_index.cc ${LIB}

clean:
	rm -f ${EXES} *.o *.exe *.a test_add bridge *.so* *.gcno *.gcda *.gcov index_composite_ut index_full_ut


