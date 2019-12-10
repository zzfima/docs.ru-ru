---
title: Аутентификация в SQL Server
ms.date: 05/22/2018
ms.assetid: 646ddbf5-dd4e-4285-8e4a-f565f666c5cc
ms.openlocfilehash: 0fb92f9e854e2a7a800335390d0195243a749b33
ms.sourcegitcommit: 42ed59871db1f29a32b3d8e7abeb20e6eceeda7c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2019
ms.locfileid: "74959970"
---
# <a name="authentication-in-sql-server"></a><span data-ttu-id="b71dc-102">Аутентификация в SQL Server</span><span class="sxs-lookup"><span data-stu-id="b71dc-102">Authentication in SQL Server</span></span>
<span data-ttu-id="b71dc-103">SQL Server поддерживает два режима проверки подлинности: режим проверки подлинности Windows и режим смешанной проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="b71dc-103">SQL Server supports two authentication modes, Windows authentication mode and mixed mode.</span></span>  
  
- <span data-ttu-id="b71dc-104">Режим проверки подлинности Windows является режимом по умолчанию. Поскольку эта модель безопасности SQL Server тесно интегрирована с Windows, зачастую ее называют встроенной функцией безопасности.</span><span class="sxs-lookup"><span data-stu-id="b71dc-104">Windows authentication is the default, and is often referred to as integrated security because this SQL Server security model is tightly integrated with Windows.</span></span> <span data-ttu-id="b71dc-105">Определенным учетным записям пользователей и групп Windows разрешается входить в SQL Server.</span><span class="sxs-lookup"><span data-stu-id="b71dc-105">Specific Windows user and group accounts are trusted to log in to SQL Server.</span></span> <span data-ttu-id="b71dc-106">Пользователи Windows, прошедшие проверку подлинности, не должны предъявлять дополнительные учетные данные.</span><span class="sxs-lookup"><span data-stu-id="b71dc-106">Windows users who have already been authenticated do not have to present additional credentials.</span></span>  
  
- <span data-ttu-id="b71dc-107">Режим смешанной проверки подлинности поддерживает проверку подлинности как средствами Windows, так и SQL Server.</span><span class="sxs-lookup"><span data-stu-id="b71dc-107">Mixed mode supports authentication both by Windows and by SQL Server.</span></span> <span data-ttu-id="b71dc-108">Пары имен пользователей и паролей ведутся в SQL Server.</span><span class="sxs-lookup"><span data-stu-id="b71dc-108">User name and password pairs are maintained within SQL Server.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="b71dc-109">Рекомендуется по возможности использовать проверку подлинности Windows.</span><span class="sxs-lookup"><span data-stu-id="b71dc-109">We recommend using Windows authentication wherever possible.</span></span> <span data-ttu-id="b71dc-110">При проверке подлинности Windows используется ряд зашифрованных сообщений для проверки подлинности пользователей в SQL Server.</span><span class="sxs-lookup"><span data-stu-id="b71dc-110">Windows authentication uses a series of encrypted messages to authenticate users in SQL Server.</span></span> <span data-ttu-id="b71dc-111">А при использовании имен входа SQL Server имена входа и зашифрованные пароли SQL Server передаются по сети, что делает их менее защищенными.</span><span class="sxs-lookup"><span data-stu-id="b71dc-111">When SQL Server logins are used, SQL Server login names and encrypted passwords are passed across the network, which makes them less secure.</span></span>  
  
 <span data-ttu-id="b71dc-112">При использовании проверки подлинности Windows пользователи уже вошли в Windows, и им не нужно отдельно входить еще и в SQL Server.</span><span class="sxs-lookup"><span data-stu-id="b71dc-112">With Windows authentication, users are already logged onto Windows and do not have to log on separately to SQL Server.</span></span> <span data-ttu-id="b71dc-113">Следующая строка `SqlConnection.ConnectionString` задает проверку подлинности Windows, не требуя имени пользователя или пароля.</span><span class="sxs-lookup"><span data-stu-id="b71dc-113">The following `SqlConnection.ConnectionString` specifies Windows authentication without requiring users to provide a user name or password.</span></span>  
  
```csharp  
"Server=MSSQL1;Database=AdventureWorks;Integrated Security=true;"
```  
  
> [!NOTE]
> <span data-ttu-id="b71dc-114">Имена входа отличаются от пользователей базы данных.</span><span class="sxs-lookup"><span data-stu-id="b71dc-114">Logins are distinct from database users.</span></span> <span data-ttu-id="b71dc-115">Имена входа или группы Windows необходимо сопоставлять с пользователями базы данных или ролями при помощи отдельной операции.</span><span class="sxs-lookup"><span data-stu-id="b71dc-115">You must map logins or Windows groups to database users or roles in a separate operation.</span></span> <span data-ttu-id="b71dc-116">После этого пользователям или ролям предоставляются разрешения на доступ к объектам базы данных.</span><span class="sxs-lookup"><span data-stu-id="b71dc-116">You then grant permissions to users or roles to access database objects.</span></span>  
  
## <a name="authentication-scenarios"></a><span data-ttu-id="b71dc-117">Сценарии проверки подлинности</span><span class="sxs-lookup"><span data-stu-id="b71dc-117">Authentication Scenarios</span></span>  
 <span data-ttu-id="b71dc-118">Обычно проверка подлинности Windows является наилучшим вариантом в следующих ситуациях.</span><span class="sxs-lookup"><span data-stu-id="b71dc-118">Windows authentication is usually the best choice in the following situations:</span></span>  
  
- <span data-ttu-id="b71dc-119">Имеется контроллер домена.</span><span class="sxs-lookup"><span data-stu-id="b71dc-119">There is a domain controller.</span></span>  
  
- <span data-ttu-id="b71dc-120">Приложение и база данных находятся на одном компьютере.</span><span class="sxs-lookup"><span data-stu-id="b71dc-120">The application and the database are on the same computer.</span></span>  
  
- <span data-ttu-id="b71dc-121">Используется экземпляр SQL Server Express или LocalDB.</span><span class="sxs-lookup"><span data-stu-id="b71dc-121">You are using an instance of SQL Server Express or LocalDB.</span></span>  
  
 <span data-ttu-id="b71dc-122">Имена входа SQL Server часто используются в следующих ситуациях.</span><span class="sxs-lookup"><span data-stu-id="b71dc-122">SQL Server logins are often used in the following situations:</span></span>  
  
- <span data-ttu-id="b71dc-123">При наличии рабочей группы.</span><span class="sxs-lookup"><span data-stu-id="b71dc-123">If you have a workgroup.</span></span>  
  
- <span data-ttu-id="b71dc-124">Пользователи подключаются из разных, не доверенных доменов.</span><span class="sxs-lookup"><span data-stu-id="b71dc-124">Users connect from different, non-trusted domains.</span></span>  
  
- <span data-ttu-id="b71dc-125">Интернет – приложения, например ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="b71dc-125">Internet applications, such as ASP.NET.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="b71dc-126">При использовании проверки подлинности Windows имена входа SQL Server не отключаются.</span><span class="sxs-lookup"><span data-stu-id="b71dc-126">Specifying Windows authentication does not disable SQL Server logins.</span></span> <span data-ttu-id="b71dc-127">Чтобы отключить имена входа SQL Server с правами доступа, используйте инструкцию Transact-SQL ALTER LOGIN DISABLE.</span><span class="sxs-lookup"><span data-stu-id="b71dc-127">Use the ALTER LOGIN DISABLE Transact-SQL statement to disable highly-privileged SQL Server logins.</span></span>  
  
## <a name="login-types"></a><span data-ttu-id="b71dc-128">Типы имен входа</span><span class="sxs-lookup"><span data-stu-id="b71dc-128">Login Types</span></span>  
 <span data-ttu-id="b71dc-129">В SQL Server существует три типа имен входа.</span><span class="sxs-lookup"><span data-stu-id="b71dc-129">SQL Server supports three types of logins:</span></span>  
  
- <span data-ttu-id="b71dc-130">Учетная запись локального пользователя Windows или учетная запись доверенного домена.</span><span class="sxs-lookup"><span data-stu-id="b71dc-130">A local Windows user account or trusted domain account.</span></span> <span data-ttu-id="b71dc-131">SQL Server доверяет проверку подлинности учетных записей пользователей Windows самой системе Windows.</span><span class="sxs-lookup"><span data-stu-id="b71dc-131">SQL Server relies on Windows to authenticate the Windows user accounts.</span></span>  
  
- <span data-ttu-id="b71dc-132">Группа пользователей Windows.</span><span class="sxs-lookup"><span data-stu-id="b71dc-132">Windows group.</span></span> <span data-ttu-id="b71dc-133">В случае предоставления доступа группе пользователей Windows право доступа получают все имена пользователей, входящие в эту группу.</span><span class="sxs-lookup"><span data-stu-id="b71dc-133">Granting access to a Windows group grants access to all Windows user logins that are members of the group.</span></span>  
  
- <span data-ttu-id="b71dc-134">Имя входа SQL Server.</span><span class="sxs-lookup"><span data-stu-id="b71dc-134">SQL Server login.</span></span> <span data-ttu-id="b71dc-135">SQL Server хранит в базе данных master имя пользователя и хэш пароля путем использования внутренних методов проверки подлинности при попытке входа в базу данных.</span><span class="sxs-lookup"><span data-stu-id="b71dc-135">SQL Server stores both the username and a hash of the password in the master database, by using internal authentication methods to verify login attempts.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="b71dc-136">SQL Server предоставляет имена входа, созданные из сертификатов или асимметричных ключей, которые используются только для подписывания кода.</span><span class="sxs-lookup"><span data-stu-id="b71dc-136">SQL Server provides logins created from certificates or asymmetric keys that are used only for code signing.</span></span> <span data-ttu-id="b71dc-137">Они не могут использоваться для подключения к SQL Server.</span><span class="sxs-lookup"><span data-stu-id="b71dc-137">They cannot be used to connect to SQL Server.</span></span>  
  
## <a name="mixed-mode-authentication"></a><span data-ttu-id="b71dc-138">Режим смешанной проверки подлинности</span><span class="sxs-lookup"><span data-stu-id="b71dc-138">Mixed Mode Authentication</span></span>  
 <span data-ttu-id="b71dc-139">При необходимости использовать режим смешанной проверки подлинности следует создать имена входа SQL Server, которые хранятся в SQL Server.</span><span class="sxs-lookup"><span data-stu-id="b71dc-139">If you must use mixed mode authentication, you must create SQL Server logins, which are stored in SQL Server.</span></span> <span data-ttu-id="b71dc-140">Затем имя пользователя и пароль SQL Server нужно будет вводить во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="b71dc-140">You then have to supply the SQL Server user name and password at run time.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="b71dc-141">SQL Server устанавливается с именем входа SQL Server `sa` (сокращение от «system administrator»).</span><span class="sxs-lookup"><span data-stu-id="b71dc-141">SQL Server installs with a SQL Server login named `sa` (an abbreviation of "system administrator").</span></span> <span data-ttu-id="b71dc-142">Назначьте имени входа `sa` надежный пароль и не используйте имя входа `sa` в приложениях.</span><span class="sxs-lookup"><span data-stu-id="b71dc-142">Assign a strong password to the `sa` login and do not use the `sa` login in your application.</span></span> <span data-ttu-id="b71dc-143">Имя входа `sa` сопоставляется предопределенной роли сервера `sysadmin`, которая имеет безотзывные административные учетные данные для всего сервера.</span><span class="sxs-lookup"><span data-stu-id="b71dc-143">The `sa` login maps to the `sysadmin` fixed server role, which has irrevocable administrative credentials on the whole server.</span></span> <span data-ttu-id="b71dc-144">Если организатор атаки получит доступ с учетными данными системного администратора, потенциальный ущерб системе может быть огромным.</span><span class="sxs-lookup"><span data-stu-id="b71dc-144">There are no limits to the potential damage if an attacker gains access as a system administrator.</span></span> <span data-ttu-id="b71dc-145">Все члены группы Windows `BUILTIN\Administrators` (группы локального администратора) по умолчанию являются членами роли `sysadmin`, но их можно удалить из этой роли.</span><span class="sxs-lookup"><span data-stu-id="b71dc-145">All members of the Windows `BUILTIN\Administrators` group (the local administrator's group) are members of the `sysadmin` role by default, but can be removed from that role.</span></span>  
  
 <span data-ttu-id="b71dc-146">SQL Server предоставляет механизмы политики паролей Windows для имен входа SQL Server.</span><span class="sxs-lookup"><span data-stu-id="b71dc-146">SQL Server provides Windows password policy mechanisms for SQL Server logins.</span></span> <span data-ttu-id="b71dc-147">Политика сложности паролей позволяет отражать атаки с использованием простого перебора путем увеличения числа возможных паролей.</span><span class="sxs-lookup"><span data-stu-id="b71dc-147">Password complexity policies are designed to deter brute force attacks by increasing the number of possible passwords.</span></span> <span data-ttu-id="b71dc-148">SQL Server могут применять те же политики сложности и срока действия к паролям, которые используются в SQL Server.</span><span class="sxs-lookup"><span data-stu-id="b71dc-148">SQL Server can apply the same complexity and expiration policies to passwords used inside SQL Server.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="b71dc-149">Объединение строк соединения из ввода пользователя может привести к уязвимости к атакам внедрения данных в строку соединения.</span><span class="sxs-lookup"><span data-stu-id="b71dc-149">Concatenating connection strings from user input can leave you vulnerable to a connection string injection attack.</span></span> <span data-ttu-id="b71dc-150">Чтобы создавать синтаксически допустимые строки соединения во время выполнения, используйте <xref:System.Data.SqlClient.SqlConnectionStringBuilder>.</span><span class="sxs-lookup"><span data-stu-id="b71dc-150">Use the <xref:System.Data.SqlClient.SqlConnectionStringBuilder> to create syntactically valid connection strings at run time.</span></span> <span data-ttu-id="b71dc-151">Дополнительные сведения см. в статье [Connection String Builders](../connection-string-builders.md) (Построители строк подключения).</span><span class="sxs-lookup"><span data-stu-id="b71dc-151">For more information, see [Connection String Builders](../connection-string-builders.md).</span></span>  
  
## <a name="external-resources"></a><span data-ttu-id="b71dc-152">Внешние ресурсы</span><span class="sxs-lookup"><span data-stu-id="b71dc-152">External Resources</span></span>  
 <span data-ttu-id="b71dc-153">Дополнительные сведения см. в следующих ресурсах.</span><span class="sxs-lookup"><span data-stu-id="b71dc-153">For more information, see the following resources.</span></span>  
  
|<span data-ttu-id="b71dc-154">Resource</span><span class="sxs-lookup"><span data-stu-id="b71dc-154">Resource</span></span>|<span data-ttu-id="b71dc-155">Описание</span><span class="sxs-lookup"><span data-stu-id="b71dc-155">Description</span></span>|  
|--------------|-----------------|  
|[<span data-ttu-id="b71dc-156">Субъекты</span><span class="sxs-lookup"><span data-stu-id="b71dc-156">Principals</span></span>](/sql/relational-databases/security/authentication-access/principals-database-engine)|<span data-ttu-id="b71dc-157">Описывает имена входа и других участников безопасности, имеющихся в SQL Server.</span><span class="sxs-lookup"><span data-stu-id="b71dc-157">Describes logins and other security principals in SQL Server.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="b71dc-158">См. также:</span><span class="sxs-lookup"><span data-stu-id="b71dc-158">See also</span></span>

- [<span data-ttu-id="b71dc-159">Защита приложений ADO.NET</span><span class="sxs-lookup"><span data-stu-id="b71dc-159">Securing ADO.NET Applications</span></span>](../securing-ado-net-applications.md)
- [<span data-ttu-id="b71dc-160">Сценарии безопасности приложений в SQL Server</span><span class="sxs-lookup"><span data-stu-id="b71dc-160">Application Security Scenarios in SQL Server</span></span>](application-security-scenarios-in-sql-server.md)
- [<span data-ttu-id="b71dc-161">Подключение к источнику данных</span><span class="sxs-lookup"><span data-stu-id="b71dc-161">Connecting to a Data Source</span></span>](../connecting-to-a-data-source.md)
- [<span data-ttu-id="b71dc-162">Строки подключения</span><span class="sxs-lookup"><span data-stu-id="b71dc-162">Connection Strings</span></span>](../connection-strings.md)
- [<span data-ttu-id="b71dc-163">Общие сведения об ADO.NET</span><span class="sxs-lookup"><span data-stu-id="b71dc-163">ADO.NET Overview</span></span>](../ado-net-overview.md)
