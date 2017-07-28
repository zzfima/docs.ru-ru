---
title: "Проверка подлинности в SQL Server | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 646ddbf5-dd4e-4285-8e4a-f565f666c5cc
caps.latest.revision: 9
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 9
---
# Проверка подлинности в SQL Server
[!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] поддерживает два режима проверки подлинности: режим проверки подлинности Windows и режим смешанной проверки подлинности.  
  
-   Режим проверки подлинности Windows является режимом по умолчанию. Поскольку эта модель безопасности [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] тесно интегрирована с Windows, часто ее называют встроенной функцией безопасности.  Определенным учетным записям пользователей и групп Windows разрешается входить в SQL Server.  Пользователи Windows, прошедшие проверку подлинности, не должны предъявлять дополнительные учетные данные.  
  
-   Режим смешанной аутентификации поддерживает проверку подлинности как средствами Windows, так и средствами [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)].  Пары имен пользователей и паролей ведутся в [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)].  
  
> [!IMPORTANT]
>  Рекомендуется по возможности использовать проверку подлинности Windows.  При проверке подлинности Windows используется ряд зашифрованных сообщений для проверки подлинности пользователей в [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)].  А при использовании имен входа [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] имена входа и пароли [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] передаются по сети, что делает их менее защищенными.  
  
 При использовании проверки подлинности Windows пользователи уже вошли в Windows и им не нужно отдельно входить еще и в [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)].  Следующая строка подключения `SqlConnection.ConnectionString` задает проверку подлинности Windows, не требуя имени пользователя или пароля.  
  
```  
"Server=MSSQL1;Database=AdventureWorks;Integrated Security=true;  
```  
  
> [!NOTE]
>  Имена входа отличаются от пользователей базы данных.  Имена входа или группы Windows необходимо сопоставлять с пользователями базы данных или ролями при помощи отдельной операции.  После этого пользователям или ролям предоставляются разрешения на доступ к объектам базы данных.  
  
## Сценарии проверки подлинности  
 Обычно проверка подлинности Windows является наилучшим вариантом в следующих ситуациях.  
  
-   Имеется контроллер домена.  
  
-   Приложение и база данных находятся на одном компьютере.  
  
-   Используется экземпляр [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] Express или LocalDB.  
  
 Имена входа SQL Server часто используются в следующих ситуациях.  
  
-   При наличии рабочей группы.  
  
-   Пользователи подключаются из разных, не доверенных доменов.  
  
-   Интернет\-приложения, например [!INCLUDE[vstecasp](../../../../../includes/vstecasp-md.md)].  
  
> [!NOTE]
>  При использовании аутентификации Windows имена входа [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] не отключаются.  Чтобы отключить имена входа [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] с высокими правами доступа, используйте инструкцию [!INCLUDE[tsql](../../../../../includes/tsql-md.md)] ALTER LOGIN DISABLE.  
  
## Типы имен входа  
 В [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] существует три типа имен входа.  
  
-   Учетная запись локального пользователя Windows или учетная запись доверенного домена.  [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] доверяет проверку подлинности учетных записей пользователей Windows самой системе Windows.  
  
-   Группа пользователей Windows.  В случае предоставления доступа группе пользователей Windows право доступа получают все имена пользователей, входящие в эту группу.  
  
-   Имя входа [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)].  [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] хранит в базе данных master имя пользователя и хэш пароля путем использования внутренних методов проверки подлинности при попытке входа в базу данных.  
  
> [!NOTE]
>  [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] предоставляет имена входа, созданные из сертификатов или асимметричных ключей, которые используются только для подписывания кода.  Они не могут использоваться для подключения к [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)].  
  
## Режим смешанной проверки подлинности  
 При необходимости использовать режим смешанной проверки подлинности следует создать имена входа [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)], которые хранятся в SQL Server.  Затем имя пользователя и пароль [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] нужно будет вводить во время выполнения.  
  
> [!IMPORTANT]
>  [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] устанавливается с именем входа [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] `sa` \(сокращение от «system administrator»\).  Назначьте имени входа `sa` надежный пароль и не используйте имя входа `sa` в приложениях.  Имя входа `sa` сопоставляется предопределенной роли сервера `sysadmin`, которая имеет безотзывные административные учетные данные для всего сервера.  Если организатор атаки получит доступ с учетными данными системного администратора, потенциальный ущерб системе может быть огромным.  Все члены группы Windows `BUILTIN\Administrators` \(группы локального администратора\) по умолчанию являются членами роли `sysadmin`, но их можно удалить из этой роли.  
  
 При работе на [!INCLUDE[winxpsvr](../../../../../includes/winxpsvr-md.md)] или более поздней версии [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] представляет механизмы политики паролей Windows для имен входа [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)].  Политика сложности паролей позволяет отражать атаки с использованием простого перебора путем увеличения числа возможных паролей.  [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] может применить к паролям, используемым в [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)], те же уровни сложности паролей и истечения срока их действия, которые применяются в [!INCLUDE[winxpsvr](../../../../../includes/winxpsvr-md.md)].  
  
> [!IMPORTANT]
>  Объединение строк соединения из ввода пользователя может привести к уязвимости к атакам внедрения данных в строку соединения.  Чтобы создавать синтаксически допустимые строки соединения во время выполнения, используйте <xref:System.Data.SqlClient.SqlConnectionStringBuilder>.  Для получения дополнительной информации см. [Построители строк подключения](../../../../../docs/framework/data/adonet/connection-string-builders.md).  
  
## Внешние ресурсы  
 Дополнительные сведения см. в следующих ресурсах.  
  
|Ресурс|Описание|  
|------------|--------------|  
|[Principals](http://msdn.microsoft.com/library/bb543165.aspx) в электронной документации [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)]|Описывает имена входа и других участников безопасности, имеющихся в [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)].|  
  
## См. также  
 [Защита приложений ADO.NET](../../../../../docs/framework/data/adonet/securing-ado-net-applications.md)   
 [Сценарии защиты приложений в SQL Server](../../../../../docs/framework/data/adonet/sql/application-security-scenarios-in-sql-server.md)   
 [Подключение к источнику данных](../../../../../docs/framework/data/adonet/connecting-to-a-data-source.md)   
 [Строки подключения](../../../../../docs/framework/data/adonet/connection-strings.md)   
 [Центр разработчиков, поставщики ADO.NET Managed Provider и набор данных](http://go.microsoft.com/fwlink/?LinkId=217917)