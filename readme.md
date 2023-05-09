1) 

Select Nom, Prenom, AnneeNaiss 

From artiste 

Where AnneeNaiss < 1950 

 

2) 

 

Select titre 

from film 

Where Genre = "Drame" 

 

3) 

Select * 

from artiste inner join role 

on artiste.idArtiste = role.idActeur 

Where idActeur = 62 

 

4) 

Select Nom, Prénom, film.IdRéalisateur 

from artiste inner join film 

on artiste.idArtiste = film.idRéalisateur 

where titre = "Memento" 

 

5) 

Select titre, Note 

from film inner join notation 

using (idFilm) 

Where titre = "Fargo" 

 

 

 

 

6) 

Select Nom, Prénom, IdArtiste 

from role inner join artiste 

on role.idActeur = artiste.idArtiste 

where role.nomRôle = "Chewbacca" 

 

7) 

 

Select Titre, NomRôle, Nom, Prénom 

from artiste inner join role 

on artiste.idArtiste = role.idActeur 

inner join film 

Where idActeur = 62 and NomRôle = "John McClane" 

 

8) 

 

Select Nom, Prénom, IdArtiste, NomRôle, titre 

from Artiste inner join role   

on artiste.idArtiste = role.idActeur 

inner join film 

on role.idFilm = film.idFilm 

Where titre = "Sueurs froides" 

 

9) 

SELECT titre as film 

from internaute inner join notation 

using (email) 

inner join film 

on notation.idFilm = film.idFilm 

Where internaute.nom = 0 and internaute.prénom = 0 

Ou 

 

SELECT titre as film 

from internaute inner join notation 

using (email) 

inner join film 

on notation.idFilm = film.idFilm 

Where internaute.nom = "Nom0" and internaute.prénom = "Prénom0" 

 

10) 

SELECT titre 

from artiste inner join role 

on artiste.idArtiste = role.idActeur 

inner join film 

Where Prénom = "Tim" and Nom = "Burton" IN (select IdActeur 

                                         from role inner join film 

                                            USING(Idfilm) 

                                            inner join artiste 

                                          

                                            Where role.idActeur = film.idRéalisateur) 

and Prénom = "Johnny" and Nom = "Depp" IN (select IdArtiste 

                                 From role inner join film 

                                 using(iDfilm) 

                                 inner join artiste 

                                 Where artiste.idArtiste = role.idActeur) 

11) 

Select titre, Nomrôle, Nom, Prénom, IdArtiste 

from artiste inner join role 

on artiste.idArtiste = role.idActeur 

inner join film using (idfilm) 

Where Prénom = "Woody" and Nom = "Allen" 

12) 

Select Prénom 

from film inner join role 

on film.idRéalisateur = role.idActeur 

inner join artiste 

on role.idActeur = artiste.idArtiste 

WHERE artiste.idArtiste = role.idActeur and role.idActeur = film.idRéalisateur 

GROUP BY Prénom 

 

13) 

SELECT titre, IdActeur, IdArtiste, Nom, Prénom 

from artiste inner join film 

inner join role 

Where Prénom = "Quentin" And Nom = "Tarantino" in (select IdActeur 

                                                   from role inner join film 

                                                   USING(IdFilm) 

                                                   inner join artiste 

                                                    

                                                  Where role.idActeur = film.idRéalisateur) 

 

14) 

SELECT titre, nom, prénom, nomrôle 

from artiste inner join role 

on artiste.idArtiste = role.idActeur 

inner join film 

where  artiste.idartiste = role.idActeur 

 

 

 

 

 

 

 

 

 

15) 

SELECT *   

from film inner join role  

on film.idRéalisateur = role.idActeur 

inner join artiste  

on role.idActeur = artiste.idArtiste 

Where IdArtiste = (SELECT idArtiste  

                   from artiste  

                   where nom = "Hitchcock" and Prénom = "Alfred") 

                   and IdActeur = (SELECT IdActeur 

                                  from role inner join artiste 

                                   on role.idActeur = artiste.idArtiste 

                                 Where Nom = "Stewart" and Prénom = "James") 

                                    