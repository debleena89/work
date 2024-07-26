# Folder Structure

```sh
.
├── Dual_core_2_ways_single_cycle.v ........ DUT
├── explorer.ebv ........................... Configuration exported from online BRISC-V explorer
├── instructions1.dat ...................... hex instruction file currently being loaded by TB
├── instructions2.dat ...................... sample instruction file containing different instructions for testing
└── tb_Dual_core_2_ways_single_cycle.v ..... TB

|-- small changes are done to supprot lw operation

|--Data cache controller and Instructin cache controller are separated to make
   the Load operation Functional. Now We are getting the particuluar value at
   the specified Register. 
|--For Store operation we are expecting that the value will not be written
   directly to memory, A write miss occurs First time as the cache is empty,
   then Read mem, data will come to Data cache and then the value at the
   specified address will be updated in the Data cache, and in the WRITE_BACK
   state that value will be stored back to memory.
```

# Usage Instructions

1. Set the path name to instructions file in TB (tb_Dual_core_2_ways_single_cycle.v)
2. Run simulation on the TB.
