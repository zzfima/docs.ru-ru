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
ms.openlocfilehash: a5a437af90f29bc601215176ad5c4fec702ddbc0
ms.sourcegitcommit: ea00c05e0995dae928d48ead99ddab6296097b4c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/02/2018
ms.locfileid: "48036082"
---
# <a name="how-to-specify-the-security-context-for-services"></a>Практическое руководство. Назначение службам контекста безопасности
По умолчанию службы работают в контексте безопасности, отличном от того, в котором работает вошедший в систему пользователь. Службы работают в контексте стандартной системной учетной записи с именем `LocalSystem`. Она дает им другие права на доступ к системным ресурсам (не такие, как у пользователя). Эту ситуацию можно изменить, указав другую учетную запись пользователя, под которой будет работать служба.  
  
 Чтобы задать контекст безопасности, для процесса, в котором выполняется служба, нужно изменить свойство <xref:System.ServiceProcess.ServiceProcessInstaller.Account%2A>. Это свойство позволяет задать для службы один из четырех типов учетных записей.  
  
-   `User`. Система запрашивает действительное имя пользователя и пароль, когда служба устанавливается и запускается в контексте учетной записи, указанной одним пользователем по сети.  
  
-   `LocalService`. Выполняется в контексте учетной записи, которая аналогична учетной записи непривилегированного пользователя локального компьютера. Удаленным серверам при этом передаются учетные данные анонимного пользователя.  
  
-   `LocalSystem`. Выполняется в контексте учетной записи, которая предоставляет широкие локальные привилегии. Удаленным серверам при этом передаются учетные данные компьютера.  
  
-   `NetworkService`. Выполняется в контексте учетной записи, которая аналогична учетной записи непривилегированного пользователя локального компьютера. Удаленным серверам при этом передаются учетные данные компьютера.  
  
 Дополнительные сведения см. в описании перечисления <xref:System.ServiceProcess.ServiceAccount>.  
  
### <a name="to-specify-the-security-context-for-a-service"></a>Назначение службам контекста безопасности  
  
1.  Создав службу, добавьте для нее необходимые установщики. Дополнительные сведения см. в [руководстве по добавлению установщиков в приложение-службу](../../../docs/framework/windows-services/how-to-add-installers-to-your-service-application.md).  
  
2.  В конструкторе откройте класс `ProjectInstaller` и щелкните установщик процессов службы, с которой вы работаете.  
  
    > [!NOTE]
    >  В классе `ProjectInstaller` для каждого приложения-службы есть по крайней мере два компонента установки: установщик процессов для всех служб в проекте и установщик для каждой службы приложения. Сейчас вам нужно выбрать <xref:System.ServiceProcess.ServiceProcessInstaller>.  
  
3.  В окне **Свойства** задайте для свойства <xref:System.ServiceProcess.ServiceProcessInstaller.Account%2A> соответствующее значение.  
  
## <a name="see-also"></a>См. также  
 [Знакомство с приложениями служб Windows](../../../docs/framework/windows-services/introduction-to-windows-service-applications.md)  
 [Практическое руководство. Добавление установщиков в приложение служб](../../../docs/framework/windows-services/how-to-add-installers-to-your-service-application.md)  
 [Практическое руководство. Создание служб Windows](../../../docs/framework/windows-services/how-to-create-windows-services.md)
