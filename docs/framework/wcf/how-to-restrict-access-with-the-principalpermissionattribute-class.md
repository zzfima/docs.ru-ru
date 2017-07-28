---
title: "Как ограничить доступ с использованием класса PrincipalPermissionAttribute | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
helpviewer_keywords: 
  - "класс PrincipalPermissionAttribute"
  - "WCF, авторизация"
  - "WCF, безопасность"
ms.assetid: 5162f5c4-8781-4cc4-9425-bb7620eaeaf4
caps.latest.revision: 23
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 23
---
# Как ограничить доступ с использованием класса PrincipalPermissionAttribute
Управление доступом к ресурсам компьютера Windows\-домена — это базовая задача обеспечения безопасности.Например, только определенные пользователи должны иметь возможность просматривать конфиденциальные данные, такие как платежные ведомости.В этом разделе рассматривается, как ограничить доступ к методу, потребовав, чтобы пользователь принадлежал к заранее заданной группе.Рабочий образец см. в разделе [Авторизация доступа к операциям службы](../../../docs/framework/wcf/samples/authorizing-access-to-service-operations.md).  
  
 Эта задача состоит из двух отдельных процедур.Первая создает группу и заносит в нее пользователей.Вторая применяет класс <xref:System.Security.Permissions.PrincipalPermissionAttribute>, чтобы задать группу.  
  
### Создание группы Windows  
  
1.  Откройте консоль **Управление компьютером**.  
  
2.  В левой панели выберите **Локальные пользователи и группы**.  
  
3.  Щелкните правой кнопкой мыши **Группы** и выберите пункт **Создать группу**.  
  
4.  В поле **Имя группы** введите имя новой группы.  
  
5.  В поле **Описание** введите описание новой группы.  
  
6.  Нажмите кнопку **Добавить**, чтобы добавить в группу новых членов.  
  
7.  Если вы добавили себя в группу и хотите протестировать приведенный ниже код, необходимо выйти из системы и снова войти в нее, чтобы быть включенным в группу.  
  
### Требование членства пользователя  
  
1.  Открыть файл кода [!INCLUDE[indigo1](../../../includes/indigo1-md.md)], содержащий реализованный код контракта службы.[!INCLUDE[crabout](../../../includes/crabout-md.md)] о реализации контракта см. в разделе [Реализация контрактов служб](../../../docs/framework/wcf/implementing-service-contracts.md)  
  
2.  Примените атрибут <xref:System.Security.Permissions.PrincipalPermissionAttribute> к каждому методу, доступ к которому необходимо ограничить определенной группой.Задайте для свойства <xref:System.Security.Permissions.SecurityAttribute.Action%2A> значение <xref:System.Security.Permissions.SecurityAction>, а для свойства <xref:System.Security.Permissions.PrincipalPermissionAttribute.Role%2A> задайте имя группы.Пример:  
  
     [!code-csharp[c_PrincipalPermissionAttribute#1](../../../samples/snippets/csharp/VS_Snippets_CFX/c_principalpermissionattribute/cs/source.cs#1)]
     [!code-vb[c_PrincipalPermissionAttribute#1](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_principalpermissionattribute/vb/source.vb#1)]  
  
    > [!NOTE]
    >  Если применить атрибут <xref:System.Security.Permissions.PrincipalPermissionAttribute> к контракту, возникает исключение <xref:System.Security.SecurityException>.Этот атрибут может применяться только на уровне метода.  
  
## Использование сертификата для управления доступом к методу  
 Для управления доступом к методу можно также использовать класс `PrincipalPermissionAttribute`, если типом учетных данных клиента является сертификат.Для этого необходимо иметь субъект и отпечаток сертификата.  
  
 Чтобы проверить свойства сертификата, см. раздел [Как просматривать сертификаты с помощью оснастки консоли MMC](../../../docs/framework/wcf/feature-details/how-to-view-certificates-with-the-mmc-snap-in.md).Чтобы определить значение отпечатка, см. раздел [Практическое руководство. Извлечение отпечатка сертификата](../../../docs/framework/wcf/feature-details/how-to-retrieve-the-thumbprint-of-a-certificate.md).  
  
#### Управление доступом с помощью сертификата  
  
1.  Примените класс <xref:System.Security.Permissions.PrincipalPermissionAttribute> к методу, доступ к которому требуется ограничить.  
  
2.  Задайте для действия атрибута значение <xref:System.Security.Permissions.SecurityAction?displayProperty=fullName>.  
  
3.  Задайте для свойства `Name` строку, состоящую из имени субъект и отпечатка сертификата.Эти два значения должны разделяться точкой с запятой и пробелом, как показано в следующем примере:  
  
     [!code-csharp[c_PrincipalPermissionAttribute#2](../../../samples/snippets/csharp/VS_Snippets_CFX/c_principalpermissionattribute/cs/source.cs#2)]
     [!code-vb[c_PrincipalPermissionAttribute#2](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_principalpermissionattribute/vb/source.vb#2)]  
  
4.  Задайте для свойства <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior.PrincipalPermissionMode%2A> значение <xref:System.ServiceModel.Description.PrincipalPermissionMode>, как показано в следующем примере конфигурации:  
  
    ```  
    <behaviors>  
      <serviceBehaviors>  
      <behavior name="SvcBehavior1">  
      <serviceAuthorization principalPermissionMode="UseAspNetRoles" />  
      </behavior>  
      </serviceBehaviors>  
    </behaviors>  
    ```  
  
     Задание для этого параметра значения `UseAspNetRoles` означает, что свойство `Name` атрибута `PrincipalPermissionAttribute` будет использоваться для строкового сравнения.При использовании сертификата в качестве учетных данных клиента [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] по умолчанию сцепляет общее имя и отпечаток сертификата с точкой с запятой, создавая уникальное значение для первичной идентификации клиента.Если в службе для режима `PrincipalPermissionMode` задано значение `UseAspNetRoles`, для определения прав доступа пользователя это значение первичной идентификации сравнивается со значением свойства `Name`.  
  
     При создании резидентной службы можно также задать свойство <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior.PrincipalPermissionMode%2A> в коде, как показано в следующем коде:  
  
     [!code-csharp[c_PrincipalPermissionAttribute#3](../../../samples/snippets/csharp/VS_Snippets_CFX/c_principalpermissionattribute/cs/source.cs#3)]
     [!code-vb[c_PrincipalPermissionAttribute#3](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_principalpermissionattribute/vb/source.vb#3)]  
  
## См. также  
 <xref:System.Security.Permissions.PrincipalPermissionAttribute>   
 <xref:System.Security.Permissions.PrincipalPermissionAttribute>   
 <xref:System.Security.Permissions.SecurityAction>   
 <xref:System.Security.Permissions.PrincipalPermissionAttribute.Role%2A>   
 [Авторизация доступа к операциям службы](../../../docs/framework/wcf/samples/authorizing-access-to-service-operations.md)   
 [Общие сведения о безопасности](../../../docs/framework/wcf/feature-details/security-overview.md)   
 [Реализация контрактов служб](../../../docs/framework/wcf/implementing-service-contracts.md)