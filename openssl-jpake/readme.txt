= Version =

The modifications were made against OpenSSL 1.0.0a and the code tested with
this same version.


= Goal =

An attacker try to impersonate a client and authenticate to the server without
knowing the shared secret.


= Testing It =

1- Run an unmodified openssl s_server compiled with J-PAKE support.

  ./apps/openssl s_server -jpake my_big_secret_string -nocert

2- Use the provided source files to replace the original files and compile
   a modified version of openssl s_client. Use this modified s_client to
   authenticate to the running server.

  ./apps/openssl s_client -jpake

  The attacker should immediately be authenticaed to the server.
