---
title: 'Tutorial: Integración de Azure Active Directory con CS Stars | Microsoft Docs'
description: Aprenda a configurar el inicio de sesión único entre Azure Active Directory y CS Stars.
services: active-directory
documentationCenter: na
author: jeevansd
manager: daveba
ms.assetid: 5704d151-afb8-40a4-b286-8bacd4f279ee
ms.service: active-directory
ms.subservice: saas-app-tutorial
ms.workload: identity
ms.tgt_pltfrm: na
ms.devlang: na
ms.topic: article
ms.date: 06/13/2017
ms.author: jeedes
ms.openlocfilehash: 6f226cab989a1ff2414c53a72a81d66749dfc4ab
ms.sourcegitcommit: d3200828266321847643f06c65a0698c4d6234da
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2019
ms.locfileid: "55153582"
---
# <a name="tutorial-azure-active-directory-integration-with-cs-stars"></a>Tutorial: Integración de Azure Active Directory con CS Stars

En este tutorial, aprenderá a integrar CS Stars con Azure Active Directory (Azure AD).

Integrar CS Stars con Azure AD proporciona las siguientes ventajas:

- Puede controlar en Azure AD quién tiene acceso a CS Stars.
- Puede permitir que los usuarios inicien sesión automáticamente en CS Stars (inicio de sesión único) con sus cuentas de Azure AD.
- Puede administrar sus cuentas en una ubicación central: el nuevo Azure Portal.

Si desea saber más sobre la integración de aplicaciones SaaS con Azure AD, consulte [¿Qué es el acceso a aplicaciones y el inicio de sesión único con Azure Active Directory?](../manage-apps/what-is-single-sign-on.md).

## <a name="prerequisites"></a>Requisitos previos

Para configurar la integración de Azure AD con CS Stars, necesita los siguientes elementos:

- Una suscripción de Azure AD
- Una suscripción habilitada para el inicio de sesión único en CS Stars

> [!NOTE]
> Para probar los pasos de este tutorial, no se recomienda el uso de un entorno de producción.

Para probar los pasos de este tutorial, debe seguir estas recomendaciones:

- No use el entorno de producción, salvo que sea necesario.
- Si no dispone de un entorno de prueba de Azure AD, puede obtener una versión de prueba de un mes [aquí](https://azure.microsoft.com/pricing/free-trial/).

## <a name="scenario-description"></a>Descripción del escenario
En este tutorial, puede probar el inicio de sesión único de Azure AD en un entorno de prueba. El escenario descrito en este tutorial consta de dos bloques de creación principales:

1. Adición de CS Stars desde la galería
1. Configuración y comprobación del inicio de sesión único de Azure AD

## <a name="adding-cs-stars-from-the-gallery"></a>Adición de CS Stars desde la galería
Para configurar la integración de CS Stars en Azure AD, deberá agregar CS Stars desde la galería a la lista de aplicaciones SaaS administradas.

**Para agregar CS Stars desde la galería, realice los pasos siguientes:**

1. En el panel de navegación izquierdo de **[Azure Portal](https://portal.azure.com)**, haga clic en el icono de **Azure Active Directory**. 

    ![Active Directory][1]

1. Vaya a **Aplicaciones empresariales**. A continuación, vaya a **Todas las aplicaciones**.

    ![APLICACIONES][2]
    
1. Para agregar una nueva aplicación, haga clic en el botón **Nueva aplicación** de la parte superior del cuadro de diálogo.

    ![APLICACIONES][3]

1. En el cuadro de búsqueda, escriba **CS Stars**.

    ![Creación de un usuario de prueba de Azure AD](./media/cs-stars-tutorial/tutorial_csstars_search.png)

1. En el panel de resultados, seleccione **CS Stars** y luego haga clic en el botón **Agregar** para agregar la aplicación.

    ![Creación de un usuario de prueba de Azure AD](./media/cs-stars-tutorial/tutorial_csstars_addfromgallery.png)

##  <a name="configuring-and-testing-azure-ad-single-sign-on"></a>Configuración y comprobación del inicio de sesión único de Azure AD
En esta sección, va a configurar y probar el inicio de sesión único de Azure AD con CS Stars con un usuario de prueba llamado "Britta Simon".

Para que el inicio de sesión único funcione, Azure AD debe saber cuál es el usuario homólogo de CS Stars para un usuario de Azure AD. Es decir, es necesario establecer una relación de vínculo entre un usuario de Azure AD y el usuario relacionado de CS Stars.

Para establecer la relación de vínculo, en CS Stars, asigne el valor de **nombre de usuario** de Azure AD como valor de **nombre de usuario**.

Para configurar y probar el inicio de sesión único de Azure AD con CS Stars, es preciso completar los siguientes bloques de creación:

1. **[Configuración del inicio de sesión único de Azure AD](#configuring-azure-ad-single-sign-on)** : para permitir a los usuarios usar esta característica.
1. **[Creación de un usuario de prueba de Azure AD](#creating-an-azure-ad-test-user)** : para probar el inicio de sesión único de Azure AD con Britta Simon.
1. **[Creación de un usuario de prueba de CS Stars](#creating-a-cs-stars-test-user)**: para tener un homólogo de Britta Simon en CS Stars que esté vinculado a la representación del usuario en Azure AD.
1. **[Asignación del usuario de prueba de Azure AD](#assigning-the-azure-ad-test-user)** : para permitir que Britta Simon use el inicio de sesión único de Azure AD.
1. **[Testing Single Sign-On](#testing-single-sign-on)** : para comprobar si funciona la configuración.

### <a name="configuring-azure-ad-single-sign-on"></a>Configuración del inicio de sesión único de Azure AD

En esta sección, habilitará el inicio de sesión único de Azure AD en Azure Portal y configurará el inicio de sesión único en la aplicación CS Stars.

**Para configurar el inicio de sesión único de Azure AD con CS Stars, realice los pasos siguientes:**

1. En Azure Portal, en la página de integración de la aplicación **CS Stars**, haga clic en **Inicio de sesión único**.

    ![Configurar inicio de sesión único][4]

1. En el cuadro de diálogo **Inicio de sesión único**, en **Modo** seleccione **Inicio de sesión basado en SAML** para habilitar el inicio de sesión único.
 
    ![Configurar inicio de sesión único](./media/cs-stars-tutorial/tutorial_csstars_samlbase.png)

1. En la sección **Dominio y direcciones URL de CS Stars**, lleve a cabo los pasos siguientes:

    ![Configurar inicio de sesión único](./media/cs-stars-tutorial/tutorial_csstars_url.png)

     a. En el cuadro de texto **URL de inicio de sesión**, escriba una dirección URL con el siguiente patrón: `https://<subdomain>.csstars.com/enterprise/default.cmdx?ssoclient=<uniqueid>`.

    b. En el cuadro de texto **Identificador**, escriba una dirección URL con el siguiente patrón: `https://<subdomain>.csstars.com/enterprise/`

    > [!NOTE] 
    > Estos valores no son reales. Debe actualizarlos con la dirección URL y el identificador reales de inicio de sesión. Póngase en contacto con el [equipo de soporte técnico de cliente de CS Stars](https://www.marshclearsight.com/support/) para obtener estos valores. 
 
1. En la sección **Certificado de firma de SAML**, haga clic en **XML de metadatos** y luego guarde el archivo de metadatos en el equipo.

    ![Configurar inicio de sesión único](./media/cs-stars-tutorial/tutorial_csstars_certificate.png) 

1. Haga clic en el botón **Guardar**.

    ![Configuración del inicio de sesión único](./media/cs-stars-tutorial/tutorial_general_400.png) 
<CS>
1. Para configurar el inicio de sesión único en **CS Stars**, necesita enviar el archivo **XML de metadatos** descargado al [equipo de soporte técnico de CS Stars](https://www.marshclearsight.com/support/). 
<CE>

> [!TIP]
> Ahora puede leer una versión resumida de estas instrucciones dentro de [Azure Portal](https://portal.azure.com) mientras configura la aplicación.  Después de agregar esta aplicación desde la sección **Active Directory > Aplicaciones empresariales**, simplemente haga clic en la pestaña **Inicio de sesión único** y acceda a la documentación insertada a través de la sección **Configuración** de la parte inferior. Puede leer más aquí sobre la característica de documentación insertada: [Documentación insertada de Azure AD]( https://go.microsoft.com/fwlink/?linkid=845985)
> 

### <a name="creating-an-azure-ad-test-user"></a>Creación de un usuario de prueba de Azure AD
El objetivo de esta sección es crear un usuario de prueba en Azure Portal llamado "Britta Simon".

![Creación de un usuario de Azure AD][100]

**Siga estos pasos para crear un usuario de prueba en Azure AD:**

1. En el panel de navegación izquierdo de **Azure Portal**, haga clic en el icono de **Azure Active Directory**.

    ![Creación de un usuario de prueba de Azure AD](./media/cs-stars-tutorial/create_aaduser_01.png) 

1. Para mostrar la lista de usuarios, vaya a **Usuarios y grupos** y haga clic en **Todos los usuarios**.
    
    ![Creación de un usuario de prueba de Azure AD](./media/cs-stars-tutorial/create_aaduser_02.png) 

1. Para abrir el cuadro de diálogo **Usuario**, haga clic en **Agregar** en la parte superior del cuadro de diálogo.
 
    ![Creación de un usuario de prueba de Azure AD](./media/cs-stars-tutorial/create_aaduser_03.png) 

1. En la página de diálogo **Usuario**, realice los siguientes pasos:
 
    ![Creación de un usuario de prueba de Azure AD](./media/cs-stars-tutorial/create_aaduser_04.png) 

     a. En el cuadro de texto **Nombre**, escriba **BrittaSimon**.

    b. En el cuadro de texto **Nombre de usuario**, escriba la **dirección de correo electrónico** de Britta Simon.

    c. Seleccione **Mostrar contraseña** y anote el valor del cuadro **Contraseña**.

    d. Haga clic en **Create**(Crear).
 
### <a name="creating-a-cs-stars-test-user"></a>Creación de un usuario de prueba de CS Stars

El objetivo de esta sección es crear una usuaria de prueba llamada Britta Simon en CS Stars.

Para obtener un usuario creado en CS Stars, debe ponerse en contacto con el [equipo de soporte técnico de CS Stars](https://www.marshclearsight.com/support/).

### <a name="assigning-the-azure-ad-test-user"></a>Asignación del usuario de prueba de Azure AD

En esta sección, habilitará a Britta Simon para que use el inicio de sesión único de Azure concediéndole acceso a CS Stars.

![Asignar usuario][200] 

**Para asignar a Britta Simon a CS Stars, realice los pasos siguientes:**

1. En Azure Portal, abra la vista de aplicaciones, navegue a la vista de directorio y vaya a **Aplicaciones empresariales**. Luego haga clic en **Todas las aplicaciones**.

    ![Asignar usuario][201] 

1. En la lista de aplicaciones, seleccione **CS Stars**.

    ![Configurar inicio de sesión único](./media/cs-stars-tutorial/tutorial_csstars_app.png) 

1. En el menú de la izquierda, haga clic en **Usuarios y grupos**.

    ![Asignar usuario][202] 

1. Haga clic en el botón **Agregar**. Después, seleccione **Usuarios y grupos** en el cuadro de diálogo **Agregar asignación**.

    ![Asignar usuario][203]

1. En el cuadro de diálogo **Usuarios y grupos**, seleccione **Britta Simon** en la lista de usuarios.

1. Haga clic en el botón **Seleccionar** del cuadro de diálogo **Usuarios y grupos**.

1. Haga clic en el botón **Asignar** del cuadro de diálogo **Agregar asignación**.
    
### <a name="testing-single-sign-on"></a>Prueba del inicio de sesión único 

El objetivo de esta sección es probar la configuración del inicio de sesión único de Azure AD mediante el panel de acceso.  
Al hacer clic en el icono de CS Stars en el Panel de acceso, debería iniciar sesión automáticamente en su aplicación CS Stars.
 

## <a name="additional-resources"></a>Recursos adicionales

* [Lista de tutoriales sobre cómo integrar aplicaciones SaaS con Azure Active Directory](tutorial-list.md)
* [¿Qué es el acceso a aplicaciones y el inicio de sesión único con Azure Active Directory?](../manage-apps/what-is-single-sign-on.md)



<!--Image references-->

[1]: ./media/cs-stars-tutorial/tutorial_general_01.png
[2]: ./media/cs-stars-tutorial/tutorial_general_02.png
[3]: ./media/cs-stars-tutorial/tutorial_general_03.png
[4]: ./media/cs-stars-tutorial/tutorial_general_04.png

[100]: ./media/cs-stars-tutorial/tutorial_general_100.png

[200]: ./media/cs-stars-tutorial/tutorial_general_200.png
[201]: ./media/cs-stars-tutorial/tutorial_general_201.png
[202]: ./media/cs-stars-tutorial/tutorial_general_202.png
[203]: ./media/cs-stars-tutorial/tutorial_general_203.png

