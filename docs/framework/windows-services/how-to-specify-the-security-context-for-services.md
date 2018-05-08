---
title: Практическое руководство. Назначение службам контекста безопасности
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Service applications, security
- security [Visual Studio], contexts
- contexts, Visual Studio security
- security [Visual Studio], service applications
- ServiceProcessInstaller class, security context
- services, security
- ServiceInstaller class, security context
ms.assetid: 02187c7b-dbf2-45f2-96c2-e11010225a22
author: ghogen
manager: douge
ms.openlocfilehash: e3e5ad7dd44dcaf1593ac80bbe6d0a367964e4e4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-specify-the-security-context-for-services"></a>Практическое руководство. Назначение службам контекста безопасности
По умолчанию службы запускаются в контексте безопасности, отличном от пользователя, вошедшего в систему. Службы выполняются в контексте системной учетной записи по умолчанию называется `LocalSystem`, что дает им разные права доступа к ресурсам системы от пользователя. Можно изменить таким образом, чтобы указать учетную запись пользователя, под которой будет запускаться служба.  
  
 Задать контекст безопасности, управляя <xref:System.ServiceProcess.ServiceProcessInstaller.Account%2A> свойство для процесса, в котором выполняется служба. Это свойство позволяет задать один из четырех типов учетных записей службы:  
  
-   `User`, чего система запрашивает допустимое имя пользователя и пароль, когда служба устанавливается и запускается в контексте учетной записи, указанной пользователем по сети;  
  
-   `LocalService`, который выполняется в контексте учетной записи, которая действует как непривилегированного пользователя локального компьютера и предоставляет учетные данные для анонимного доступа к удаленным серверам;  
  
-   `LocalSystem`, который выполняется в контексте учетной записи, которая предоставляет широкие локальные привилегии и передает учетные данные компьютера удаленным серверам;  
  
-   `NetworkService`, который выполняется в контексте учетной записи, которая действует как непривилегированного пользователя локального компьютера и предоставляет учетные данные компьютера удаленным серверам.  
  
 Дополнительные сведения см. в описании перечисления <xref:System.ServiceProcess.ServiceAccount>.  
  
### <a name="to-specify-the-security-context-for-a-service"></a>Чтобы указать контекст безопасности для службы  
  
1.  После создания службы, добавьте установщики, необходимые для него. Дополнительные сведения см. в разделе [как: добавление установщиков к приложению службы](../../../docs/framework/windows-services/how-to-add-installers-to-your-service-application.md).  
  
2.  В конструкторе, доступ к `ProjectInstaller` класса и нажмите кнопку установщик процессов службы для службы, вы работаете.  
  
    > [!NOTE]
    >  Для каждого приложения служб есть по крайней мере два компонента установки в `ProjectInstaller` класса — компонент, устанавливающий процессы для всех служб в проекте и установщик для каждой службы, приложение содержит. В этом случае нужно выбрать <xref:System.ServiceProcess.ServiceProcessInstaller>.  
  
3.  В **свойства** задайте <xref:System.ServiceProcess.ServiceProcessInstaller.Account%2A> соответствующее значение.  
  
## <a name="see-also"></a>См. также  
 [Знакомство с приложениями служб Windows](../../../docs/framework/windows-services/introduction-to-windows-service-applications.md)  
 [Практическое руководство. Добавление установщиков в приложение служб](../../../docs/framework/windows-services/how-to-add-installers-to-your-service-application.md)  
 [Практическое руководство. Создание служб Windows](../../../docs/framework/windows-services/how-to-create-windows-services.md)
