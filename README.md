- 👋 Hi, I’m @LohUlises
- 👀 I’m interested in ...
- 🌱 I’m currently learning ...
- 💞️ I’m looking to collaborate on ...
- 📫 How to reach me ...


padece(pedro,gripe).
padece(pedro,hepatitis).
padece(juan,hepatitis).
padece(maria,gripe).
padece(carlos,intoxicacion).

sintoma(fiebre,gripe).
sintoma(cansancio,hepatitis).
sintoma(diarrea,intoxicacion).
sintoma(cansancio,gripe).

pastillaT(aspirina,fiebre).
pastillaT(lomotil,diarrea).
    
%X=Farmaco.
%Y=Enfermedad.
%Z=Dolencia.

alivia(X,Y):-
	sintoma(Z,Y),
	pastillaT(X,Z).
		
%X=PERSONA
%Y=FARMACO
%Z=ENFERMEDAD

tomar(X,Y):-
	padece(X,Z),
	alivia(Y,Z). 

%X=PERSONA
%Y=SINTOMA
%Z=DOLENCIA

sintomas(X,Y):-
	padece(X,Z),
	sintoma(Y,Z).
	
%X=PERSONA 1
%Y=PERSONA 2
%Z=sintoma en comun

comparten(X,Y,Z):-
	sintomas(X,Z),
	sintomas(Y,A),
	X\==Y,
	Z\==A.
