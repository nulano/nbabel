
CC=gcc
CXX=g++

bench0:
	python bench0.py ../data/input16

bench_pypy_purepy:
	pypy bench_purepy.py ../data/input16

bench_pypy:
	pypy bench_pypy.py ../data/input16

bench1k: __pythran__/bench.py
	time python bench.py ../data/input1k

bench1k_opti: __pythran__/bench_more_opti.py
	time python bench_more_opti.py ../data/input1k

bench2k: __pythran__/bench.py
	time python bench.py ../data/input2k

bench16k: __pythran__/bench.py
	time python bench.py ../data/input16k 0.2

bench256: __pythran__/bench.py
	python bench.py ../data/input256

bench128: __pythran__/bench.py
	python bench.py ../data/input128

bench64: __pythran__/bench.py
	python bench.py ../data/input64

__pythran__/bench.py: bench.py
	transonic bench.py -af "-march=native -Ofast"
	# transonic bench.py -af "-march=native -DUSE_XSIMD -Ofast"

__pythran__/bench_more_opti.py: bench_more_opti.py
	transonic bench_more_opti.py -af "-march=native -Ofast"

clean:
	rm -rf __pythran__
