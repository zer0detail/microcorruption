# Montevideo

Montevideo is the 7th challenge in the microcorruption series.
there's not much in these patch notes other than the software has been rewritten with secure coding practices.

![changes](Images/Montevideo/changes.png)



So looking over this code there really isn't much different apart from the program now using strcopy and memset.

![login](Images/Montevideo/login.png)

Everything else is the same.

Before anything, I just want to test and see if this has fixed the buffer overflow in the password when login returns.

![attempt](Images/Montevideo/attempt.png)

entering a long password and then continuing on to a breakpoint set at the "ret" for the login function and then stepping once I can see that PC is still overwritten with 4141

![overflow](Images/Montevideo/attempt.png)

Actually, the overwritten return address is still at exactly the same offset.
The interrupt call I jumped to in the last exercise to call my own  interrupt is also still at the same offset...

The payload from the last exercise should..

![payload](Images/Montevideo/payload.png)

work.

![success](Images/Montevideo/success.png)
