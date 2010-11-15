= Version =

The modifications were made against OpenSSH 5.5 and the code tested with this
same version.


= Goal =

An attacker try authenticate to an SSH server without knowing user's secret.


= Testing It =

1- Run an unmodified sshd server compiled with J-PAKE support and accepting
   J-PAKE authentications.

2- Use the provided source files to compile a modified version of the ssh
   client. This version is used by the attacker to authenticate itself with
   the running server.

  ./ssh -o "ZeroKnowledgePasswordAuthentication yes" user@host

   The attacker should immediately be authenticaed to the server without having
   to provide any password.
