### issue Remote attestation testing

https://github.com/openenclave/openenclave/issues/2114


```
spalacio@oats3:~/repos/openenclave/build/samples/remote_attestation$ OE_LOG_LEVEL=INFO make run
[ 18%] Built target remote_attestation_host
[ 22%] Built target public_key_a
[ 50%] Built target common
[ 63%] Built target enclave_b
[ 72%] Built target enclave_b_signed
[ 77%] Built target public_key_b
[ 90%] Built target enclave_a
[100%] Built target enclave_a_signed
[100%] Built target sign
Host: Creating two enclaves
Host: Enclave library /home/spalacio/repos/openenclave/build/samples/remote_attestation/enclave_$/enclave_a.signed
2020-04-21T22:30:18.000000Z [(H)INFO] tid(0x7fb2428ca740) | Processor supports AVX instructions $/home/spalacio/repos/openenclave/host/sgx/linux/xstate.c:_is_xgetbv_supported:33]
2020-04-21T22:30:18.000000Z [(H)INFO] tid(0x7fb2428ca740) | Value of XFRM to be set in enclave i$ 7
 [/home/spalacio/repos/openenclave/host/sgx/sgxload.c:_detect_xfrm:121]
Enclave: ***/home/spalacio/repos/openenclave/build/install/opt/openenclave/share/openenclave/sam$les/remote_attestation/common/crypto.cpp(76): mbedtls initialized.
Host: Enclave successfully created.
Host: Enclave library /home/spalacio/repos/openenclave/build/samples/remote_attestation/enclave_$/enclave_b.signed
2020-04-21T22:30:18.000000Z [(H)INFO] tid(0x7fb2428ca740) | Processor supports AVX instructions $/home/spalacio/repos/openenclave/host/sgx/linux/xstate.c:_is_xgetbv_supported:33]
2020-04-21T22:30:18.000000Z [(H)INFO] tid(0x7fb2428ca740) | Value of XFRM to be set in enclave i$ 7
 [/home/spalacio/repos/openenclave/host/sgx/sgxload.c:_detect_xfrm:121]
Enclave: ***/home/spalacio/repos/openenclave/build/install/opt/openenclave/share/openenclave/sam$les/remote_attestation/common/crypto.cpp(76): mbedtls initialized.
Host: Enclave successfully created.
Host: requesting a remote report and the encryption key from 1st enclave
Enclave: ***/home/spalacio/repos/openenclave/build/install/opt/openenclave/share/openenclave/sam$les/remote_attestation/enclave_a/ecalls.cpp(43): enter get_remote_report_with_pubkey
Enclave: ***/home/spalacio/repos/openenclave/build/install/opt/openenclave/share/openenclave/sam$les/remote_attestation/common/dispatcher.cpp(96): get_remote_report_with_pubkey
2020-04-21T22:30:19.000000Z [(H)INFO] tid(0x7fb2428ca740) | oe_load_quote_provider libdcap_quote$rov.so
 [/home/spalacio/repos/openenclave/host/sgx/linux/sgxquoteproviderloader.c:oe_load_quote_provide$:25]
2020-04-21T22:30:19.000000Z [(H)ERROR] tid(0x7fb2428ca740) | sgxquoteprovider: libdcap_quoteprov$so libdcap_quoteprov.so: cannot open shared object file: No such file or directory
 [/home/spalacio/repos/openenclave/host/sgx/linux/sgxquoteproviderloader.c:oe_load_quote_provide$:80]
2020-04-21T22:30:19.000000Z [(H)ERROR] tid(0x7fb2428ca740) | oe_initialize_quote_provider failed
(oe_result_t=OE_QUOTE_PROVIDER_LOAD_ERROR) [/home/spalacio/repos/openenclave/host/sgx/sgxquotepr$vider.c:oe_initialize_quote_provider:51]
2020-04-21T22:30:19.000000Z [(H)ERROR] tid(0x7fb2428ca740) | :OE_QUOTE_PROVIDER_LOAD_ERROR [/hom$/spalacio/repos/openenclave/host/sgx/quote.c:sgx_get_qetarget_info:30]
2020-04-21T22:30:19.000000Z [(E)ERROR] tid(0x7fb2428ca740) | enclave_a.signed::OE_QUOTE_PROVIDER$LOAD_ERROR [/home/spalacio/repos/openenclave/enclave/core/sgx/report.c:oe_get_remote_report:182]
2020-04-21T22:30:19.000000Z [(E)ERROR] tid(0x7fb2428ca740) | enclave_a.signed::OE_QUOTE_PROVIDER$
2020-04-21T22:30:19.000000Z [(E)ERROR] tid(0x7fb2428ca740) | enclave_a.signed::OE_QUOTE_PROVIDER_
LOAD_ERROR [/home/spalacio/repos/openenclave/enclave/core/sgx/report.c:oe_get_report_v2:332]
Enclave: ***/home/spalacio/repos/openenclave/build/install/opt/openenclave/share/openenclave/samp
les/remote_attestation/common/attestation.cpp(54): oe_get_report failed.
Enclave: ***/home/spalacio/repos/openenclave/build/install/opt/openenclave/share/openenclave/samp
les/remote_attestation/common/dispatcher.cpp(137): get_remote_report_with_pubkey failed.
Host: verify_report_and_set_pubkey failed. OE_OKHost: Terminating enclaves
Enclave: ***/home/spalacio/repos/openenclave/build/install/opt/openenclave/share/openenclave/samp
les/remote_attestation/common/crypto.cpp(90): mbedtls cleaned up.
Host: Enclave successfully terminated.
Enclave: ***/home/spalacio/repos/openenclave/build/install/opt/openenclave/share/openenclave/samp
les/remote_attestation/common/crypto.cpp(90): mbedtls cleaned up.
Host: Enclave successfully terminated.
Host:  failed
CMakeFiles/run.dir/build.make:57: recipe for target 'CMakeFiles/run' failed
make[3]: *** [CMakeFiles/run] Error 1
CMakeFiles/Makefile2:111: recipe for target 'CMakeFiles/run.dir/all' failed
make[2]: *** [CMakeFiles/run.dir/all] Error 2
CMakeFiles/Makefile2:118: recipe for target 'CMakeFiles/run.dir/rule' failed
make[1]: *** [CMakeFiles/run.dir/rule] Error 2
Makefile:131: recipe for target 'run' failed
make: *** [run] Error 2