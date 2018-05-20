# professor.h
///clase maestra de los datos del profesor
#ifndef PROFESSOR_H_INCLUDED
#define PROFESSOR_H_INCLUDED

/*** Cabeceras del sistema ***/
#include <string>

/*** Cabeceras locales***/
#include "listexception.h"          ///Excepciones de lista
#include "name.h"                   ///Registrar nombres validos
#include "date.h"                   ///Registrar fechas validas
#include "address.h"                ///Registrar domicilios
#include "personaldata.h"           ///Datos personales
#include "academicformation.h"      ///Formación académica
#include "academicproduction.h"     ///Produccion académica
#include "teaching.h"               ///Docencia (Clases impartidas)
#include "tutorials.h"              ///Tutorias (Alumnos tutorados)

class Professor{
    private:
        ///Atributos
        PersonalData data;
        Formation school[10];
        AcademicProduction perfomance[10];
        Teaching courses[10];
        Tutorials student[15];

        ///Atributos (LISTAS)
        int formacion;      ///Ancla de Lista (FORMACION ACADEMICA)
        int produccion;     ///Ancla de Lista (PRODUCCION ACADEMICA)
        int docencia;       ///Ancla de Lista (DOCENCIA)
        int tutoria;        ///Ancla de Lista (TUTORIAS)

    public:
        Professor();
        /******************************** DATOS PERSONALES ****************************************/
        void setData(PersonalData& );
        PersonalData getData();

        /******************************** FORMACION ACADEMICA ****************************************/
        bool emptyFormation();
        bool fullFormation();
        void insertFormation(int& ,Formation&);     ///Recibe (posición en el arreglo, objeto)
        void deleteFormation(int& );     ///Recibe (posición en el arreglo)

        int getLastFormation();
        int getFirstFormation();

        Formation returnFormation(const int&);     ///Recibe (posición) - Retorna (objeto)
        bool findFormation(std::string&);               ///Recibe(id cedula) - retorna(bandera) [busca un dato]
        std::string toStringFormation();             ///Imprime lista

        /******************************** PRODUCCION ACADEMICA ****************************************/
        bool emptyProduction();
        bool fullProduction();
        void insertProduction(int& ,AcademicProduction&);     ///Recibe (posición en el arreglo, objeto)
        void deleteProduction(int& );     ///Recibe (posición en el arreglo)

        int getLastProduction();
        int getFirstProduction();

        AcademicProduction returnProduction(const int&);     ///Recibe (posición) - Retorna (objeto)
        bool findProduction(std::string&);               ///Recibe(id registro) - retorna(bandera) [busca un dato]
        std::string toStringProduction();             ///Imprime lista

        /******************************** DOCENCIA ****************************************/
        bool emptyCourses();
        bool fullCourses();
        void insertCourses(int& ,Teaching&);     ///Recibe (posición en el arreglo, objeto)
        void deleteCourses(int& );     ///Recibe (posición en el arreglo)

        int getLastCourses();
        int getFirstCourses();

        Teaching returnCourse(const int&);     ///Recibe (posición) - Retorna (objeto)
        bool findCourses(std::string&);               ///Recibe(nombre) - retorna(bandera) [busca un dato]
        std::string toStringCourses();             ///Imprime lista

        /******************************** TUTORIAS ****************************************/
        bool emptyTutorial();
        bool fullTutorial();
        void insertTutorial(int& ,Tutorials&);     ///Recibe (posición en el arreglo, objeto)
        void deleteTutorial(int& );     ///Recibe (posición en el arreglo)

        int getLastTutorial();
        int getFirstTutorial();

        Tutorials returnTutorial(const int&);     ///Recibe (posición) - Retorna (objeto)
        bool findTutorial(Name&);               ///Recibe(nombre) - retorna(bandera) [busca un dato]
        std::string toStringTutorial();             ///Imprime lista

};

#endif // PROFESSOR_H_INCLUDED
