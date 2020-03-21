---
title: Настраиваемое действие SendMail
ms.date: 03/30/2017
ms.assetid: 947a9ae6-379c-43a3-9cd5-87f573a5739f
ms.openlocfilehash: e7cc64e68c3d78b9ee7ec813700e96a52c239141
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182780"
---
# <a name="sendmail-custom-activity"></a><span data-ttu-id="a36aa-102">Настраиваемое действие SendMail</span><span class="sxs-lookup"><span data-stu-id="a36aa-102">SendMail Custom Activity</span></span>
<span data-ttu-id="a36aa-103">В образце описывается создание настраиваемого действия, которое является производным от <xref:System.Activities.AsyncCodeActivity>, для отправки почты с помощью SMTP для работы в приложении рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="a36aa-103">This sample demonstrates how to create a custom activity that derives from <xref:System.Activities.AsyncCodeActivity> to send mail using SMTP for use within a workflow application.</span></span> <span data-ttu-id="a36aa-104">Пользовательская деятельность использует <xref:System.Net.Mail.SmtpClient> возможности для асинхронного отправки электронной почты и отправки почты с аутентификацией.</span><span class="sxs-lookup"><span data-stu-id="a36aa-104">The custom activity uses the capabilities of <xref:System.Net.Mail.SmtpClient> to send email asynchronously and to send mail with authentication.</span></span> <span data-ttu-id="a36aa-105">При этом также обеспечивается возможность использования таких возможностей конечных пользователей, как тестовый режим, замена маркеров, шаблоны файлов и тестовый путь размещения файла.</span><span class="sxs-lookup"><span data-stu-id="a36aa-105">It also provides some end-user features like test mode, token replacement, file templates, and test drop path.</span></span>  
  
 <span data-ttu-id="a36aa-106">В следующей таблице представлены аргументы для действия `SendMail`.</span><span class="sxs-lookup"><span data-stu-id="a36aa-106">The following table details the arguments for the `SendMail` activity.</span></span>  
  
|<span data-ttu-id="a36aa-107">Имя</span><span class="sxs-lookup"><span data-stu-id="a36aa-107">Name</span></span>|<span data-ttu-id="a36aa-108">Тип</span><span class="sxs-lookup"><span data-stu-id="a36aa-108">Type</span></span>|<span data-ttu-id="a36aa-109">Описание</span><span class="sxs-lookup"><span data-stu-id="a36aa-109">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="a36aa-110">Узел</span><span class="sxs-lookup"><span data-stu-id="a36aa-110">Host</span></span>|<span data-ttu-id="a36aa-111">Строка</span><span class="sxs-lookup"><span data-stu-id="a36aa-111">String</span></span>|<span data-ttu-id="a36aa-112">Адрес узла SMTP-сервера.</span><span class="sxs-lookup"><span data-stu-id="a36aa-112">Address of the SMTP server host.</span></span>|  
|<span data-ttu-id="a36aa-113">Порт</span><span class="sxs-lookup"><span data-stu-id="a36aa-113">Port</span></span>|<span data-ttu-id="a36aa-114">Строка</span><span class="sxs-lookup"><span data-stu-id="a36aa-114">String</span></span>|<span data-ttu-id="a36aa-115">Порт службы SMTP на узле.</span><span class="sxs-lookup"><span data-stu-id="a36aa-115">Port of the SMTP service in the host.</span></span>|  
|<span data-ttu-id="a36aa-116">EnableSsl</span><span class="sxs-lookup"><span data-stu-id="a36aa-116">EnableSsl</span></span>|<span data-ttu-id="a36aa-117">bool</span><span class="sxs-lookup"><span data-stu-id="a36aa-117">bool</span></span>|<span data-ttu-id="a36aa-118">Указывает, использует ли <xref:System.Net.Mail.SmtpClient> протокол SSL для шифрования соединения.</span><span class="sxs-lookup"><span data-stu-id="a36aa-118">Specifies whether the <xref:System.Net.Mail.SmtpClient> uses Secure Sockets Layer (SSL) to encrypt the connection.</span></span>|  
|<span data-ttu-id="a36aa-119">UserName</span><span class="sxs-lookup"><span data-stu-id="a36aa-119">UserName</span></span>|<span data-ttu-id="a36aa-120">Строка</span><span class="sxs-lookup"><span data-stu-id="a36aa-120">String</span></span>|<span data-ttu-id="a36aa-121">Имя пользователя для настройки учетных данных для проверки подлинности свойства <xref:System.Net.Mail.SmtpClient.Credentials%2A> отправителя.</span><span class="sxs-lookup"><span data-stu-id="a36aa-121">Username to set up the credentials to authenticate the sender <xref:System.Net.Mail.SmtpClient.Credentials%2A> property.</span></span>|  
|<span data-ttu-id="a36aa-122">Пароль</span><span class="sxs-lookup"><span data-stu-id="a36aa-122">Password</span></span>|<span data-ttu-id="a36aa-123">Строка</span><span class="sxs-lookup"><span data-stu-id="a36aa-123">String</span></span>|<span data-ttu-id="a36aa-124">Пароль для настройки учетных данных для проверки подлинности свойства <xref:System.Net.Mail.SmtpClient.Credentials%2A> отправителя.</span><span class="sxs-lookup"><span data-stu-id="a36aa-124">Password to set up the credentials to authenticate the sender <xref:System.Net.Mail.SmtpClient.Credentials%2A> property.</span></span>|  
|<span data-ttu-id="a36aa-125">Тема</span><span class="sxs-lookup"><span data-stu-id="a36aa-125">Subject</span></span>|<span data-ttu-id="a36aa-126"><xref:System.Activities.InArgument%601>\<струнная></span><span class="sxs-lookup"><span data-stu-id="a36aa-126"><xref:System.Activities.InArgument%601>\<string></span></span>|<span data-ttu-id="a36aa-127">Тема сообщения.</span><span class="sxs-lookup"><span data-stu-id="a36aa-127">Subject of the message.</span></span>|  
|<span data-ttu-id="a36aa-128">Текст</span><span class="sxs-lookup"><span data-stu-id="a36aa-128">Body</span></span>|<span data-ttu-id="a36aa-129"><xref:System.Activities.InArgument%601>\<струнная></span><span class="sxs-lookup"><span data-stu-id="a36aa-129"><xref:System.Activities.InArgument%601>\<string></span></span>|<span data-ttu-id="a36aa-130">Текст сообщения.</span><span class="sxs-lookup"><span data-stu-id="a36aa-130">Body of the message.</span></span>|  
|<span data-ttu-id="a36aa-131">Вложения</span><span class="sxs-lookup"><span data-stu-id="a36aa-131">Attachments</span></span>|<span data-ttu-id="a36aa-132"><xref:System.Activities.InArgument%601>\<струнная></span><span class="sxs-lookup"><span data-stu-id="a36aa-132"><xref:System.Activities.InArgument%601>\<string></span></span>|<span data-ttu-id="a36aa-133">Сбор приложений, используемый для хранения данных, прикрепленных к этому сообщению электронной почты.</span><span class="sxs-lookup"><span data-stu-id="a36aa-133">Attachment collection used to store data attached to this email message.</span></span>|  
|<span data-ttu-id="a36aa-134">От</span><span class="sxs-lookup"><span data-stu-id="a36aa-134">From</span></span>|<xref:System.Net.Mail.MailAddress>|<span data-ttu-id="a36aa-135">С адреса для этого сообщения электронной почты.</span><span class="sxs-lookup"><span data-stu-id="a36aa-135">From address for this email message.</span></span>|  
|<span data-ttu-id="a36aa-136">Чтобы</span><span class="sxs-lookup"><span data-stu-id="a36aa-136">To</span></span>|<xref:System.Activities.InArgument%601>\<<xref:System.Net.Mail.MailAddressCollection>>|<span data-ttu-id="a36aa-137">Коллекция адресов, содержащая получателей этого сообщения электронной почты.</span><span class="sxs-lookup"><span data-stu-id="a36aa-137">Address collection that contains the recipients of this email message.</span></span>|  
|<span data-ttu-id="a36aa-138">CC</span><span class="sxs-lookup"><span data-stu-id="a36aa-138">CC</span></span>|<xref:System.Activities.InArgument%601>\<<xref:System.Net.Mail.MailAddressCollection>>|<span data-ttu-id="a36aa-139">Коллекция адресов, содержащая получателей копии углерода (CC) для этого сообщения электронной почты.</span><span class="sxs-lookup"><span data-stu-id="a36aa-139">Address collection that contains the carbon copy (CC) recipients for this email message.</span></span>|  
|<span data-ttu-id="a36aa-140">BCC</span><span class="sxs-lookup"><span data-stu-id="a36aa-140">BCC</span></span>|<xref:System.Activities.InArgument%601>\<<xref:System.Net.Mail.MailAddressCollection>>|<span data-ttu-id="a36aa-141">Коллекция адресов, содержащая получателей слепой копии углерода (BCC) для этого сообщения электронной почты.</span><span class="sxs-lookup"><span data-stu-id="a36aa-141">Address collection that contains the blind carbon copy (BCC) recipients for this email message.</span></span>|  
|<span data-ttu-id="a36aa-142">Токены</span><span class="sxs-lookup"><span data-stu-id="a36aa-142">Tokens</span></span>|<span data-ttu-id="a36aa-143"><xref:System.Activities.InArgument%601><строка\<IDictionary, струнная>></span><span class="sxs-lookup"><span data-stu-id="a36aa-143"><xref:System.Activities.InArgument%601><IDictionary\<string, string>></span></span>|<span data-ttu-id="a36aa-144">Маркеры для замены в тексте.</span><span class="sxs-lookup"><span data-stu-id="a36aa-144">Tokens to replace in the body.</span></span> <span data-ttu-id="a36aa-145">Эта возможность позволяет пользователям указывать определенные значением в тексте сообщения, которые можно позднее заменить маркерами, предоставляемыми при использовании этого свойства.</span><span class="sxs-lookup"><span data-stu-id="a36aa-145">This feature allows users to specify some values in the body than can be replaced later by the tokens provided using this property.</span></span>|  
|<span data-ttu-id="a36aa-146">BodyTemplateFilePath</span><span class="sxs-lookup"><span data-stu-id="a36aa-146">BodyTemplateFilePath</span></span>|<span data-ttu-id="a36aa-147">Строка</span><span class="sxs-lookup"><span data-stu-id="a36aa-147">String</span></span>|<span data-ttu-id="a36aa-148">Путь к шаблону текста.</span><span class="sxs-lookup"><span data-stu-id="a36aa-148">Path of a template for the body.</span></span> <span data-ttu-id="a36aa-149">Действие `SendMail` копирует содержимое этого файла в свойство текста.</span><span class="sxs-lookup"><span data-stu-id="a36aa-149">The `SendMail` activity copies the contents of this file to its body property.</span></span><br /><br /> <span data-ttu-id="a36aa-150">Этот шаблон может содержать токены, которые заменяются на содержимое свойства Tokens.</span><span class="sxs-lookup"><span data-stu-id="a36aa-150">The template can contain tokens that are replaced by the contents of the tokens property.</span></span>|  
|<span data-ttu-id="a36aa-151">TestMailTo</span><span class="sxs-lookup"><span data-stu-id="a36aa-151">TestMailTo</span></span>|<xref:System.Net.Mail.MailAddress>|<span data-ttu-id="a36aa-152">Когда это свойство установлено, все электронные письма отправляются на указанный в нем адрес.</span><span class="sxs-lookup"><span data-stu-id="a36aa-152">When this property is set, all emails are sent to the address specified in it.</span></span><br /><br /> <span data-ttu-id="a36aa-153">Это свойство планируется использовать при тестировании рабочих процессов.</span><span class="sxs-lookup"><span data-stu-id="a36aa-153">This property is intended to be used when testing workflows.</span></span> <span data-ttu-id="a36aa-154">Например, если вы хотите убедиться, что все письма отправляются без отправки их фактическим получателям.</span><span class="sxs-lookup"><span data-stu-id="a36aa-154">For example, when you want to make sure that all emails are sent without sending them to the actual recipients.</span></span>|  
|<span data-ttu-id="a36aa-155">TestDropPath</span><span class="sxs-lookup"><span data-stu-id="a36aa-155">TestDropPath</span></span>|<span data-ttu-id="a36aa-156">Строка</span><span class="sxs-lookup"><span data-stu-id="a36aa-156">String</span></span>|<span data-ttu-id="a36aa-157">Когда это свойство установлено, все сообщения электронной почты также сохраняются в указанном файле.</span><span class="sxs-lookup"><span data-stu-id="a36aa-157">When this property is set, all emails are also saved in the specified file.</span></span><br /><br /> <span data-ttu-id="a36aa-158">Это свойство предназначено для использования при тестировании или отладке рабочих процессов, чтобы убедиться, что формат и содержимые письма является подходящим.</span><span class="sxs-lookup"><span data-stu-id="a36aa-158">This property is intended to be used when you are testing or debugging workflows, to make sure that the format and contents of the outgoing emails is appropriate.</span></span>|  
  
## <a name="solution-contents"></a><span data-ttu-id="a36aa-159">Содержимое решения</span><span class="sxs-lookup"><span data-stu-id="a36aa-159">Solution Contents</span></span>  
 <span data-ttu-id="a36aa-160">Решение содержит два проекта.</span><span class="sxs-lookup"><span data-stu-id="a36aa-160">The solution contains two projects.</span></span>  
  
|<span data-ttu-id="a36aa-161">Проект</span><span class="sxs-lookup"><span data-stu-id="a36aa-161">Project</span></span>|<span data-ttu-id="a36aa-162">Описание</span><span class="sxs-lookup"><span data-stu-id="a36aa-162">Description</span></span>|<span data-ttu-id="a36aa-163">Важные файлы</span><span class="sxs-lookup"><span data-stu-id="a36aa-163">Important Files</span></span>|  
|-------------|-----------------|---------------------|  
|<span data-ttu-id="a36aa-164">SendMail</span><span class="sxs-lookup"><span data-stu-id="a36aa-164">SendMail</span></span>|<span data-ttu-id="a36aa-165">Действие SendMail</span><span class="sxs-lookup"><span data-stu-id="a36aa-165">The SendMail activity</span></span>|<span data-ttu-id="a36aa-166">1. SendMail.cs: реализация для основного мероприятия</span><span class="sxs-lookup"><span data-stu-id="a36aa-166">1.  SendMail.cs: implementation for the main activity</span></span><br /><span data-ttu-id="a36aa-167">2. SendMailDesigner.xaml и SendMailDesigner.xaml.cs: конструктор для деятельности SendMail</span><span class="sxs-lookup"><span data-stu-id="a36aa-167">2.  SendMailDesigner.xaml and SendMailDesigner.xaml.cs: designer for the SendMail activity</span></span><br /><span data-ttu-id="a36aa-168">3. MailTemplateBody.htm: шаблон для электронной почты, которая будет отправлена.</span><span class="sxs-lookup"><span data-stu-id="a36aa-168">3.  MailTemplateBody.htm: template for the email to be sent out.</span></span>|  
|<span data-ttu-id="a36aa-169">SendMailTestClient</span><span class="sxs-lookup"><span data-stu-id="a36aa-169">SendMailTestClient</span></span>|<span data-ttu-id="a36aa-170">Клиент для тестирования действий SendMail.</span><span class="sxs-lookup"><span data-stu-id="a36aa-170">Client to test the SendMail activity.</span></span>  <span data-ttu-id="a36aa-171">В этом проекте описываются два способа вызова действия SendMail: декларативно и программно.</span><span class="sxs-lookup"><span data-stu-id="a36aa-171">This project demonstrates two ways of invoking the SendMail activity: declaratively, and programmatically.</span></span>|<span data-ttu-id="a36aa-172">1. Sequence1.xaml: рабочий процесс, который вызывает активность SendMail.</span><span class="sxs-lookup"><span data-stu-id="a36aa-172">1.  Sequence1.xaml: workflow that invokes the SendMail activity.</span></span><br /><span data-ttu-id="a36aa-173">2. Program.cs: вызывает Sequence1, а также создает рабочий процесс программно, который использует SendMail.</span><span class="sxs-lookup"><span data-stu-id="a36aa-173">2.  Program.cs: invokes Sequence1 and also creates a workflow programmatically that uses SendMail.</span></span>|  
  
## <a name="further-configuration-of-the-sendmail-activity"></a><span data-ttu-id="a36aa-174">Дополнительная настройка действия SendMail</span><span class="sxs-lookup"><span data-stu-id="a36aa-174">Further configuration of the SendMail activity</span></span>  
 <span data-ttu-id="a36aa-175">Хотя она не показана в образце, пользователи могут выполнять дополнительную настройку действия SendMail.</span><span class="sxs-lookup"><span data-stu-id="a36aa-175">Although not shown in the sample, users can perform addition configuration of the SendMail activity.</span></span> <span data-ttu-id="a36aa-176">Эта дополнительная настройка описывается в следующих трех разделах.</span><span class="sxs-lookup"><span data-stu-id="a36aa-176">The next three sections demonstrate how this is done.</span></span>  
  
### <a name="sending-an-email-using-tokens-specified-in-the-body"></a><span data-ttu-id="a36aa-177">Отправка сообщения электронной почты с использованием маркеров, указанных в тексте сообщения</span><span class="sxs-lookup"><span data-stu-id="a36aa-177">Sending an email using tokens specified in the body</span></span>  
 <span data-ttu-id="a36aa-178">В этом фрагменте кода описывается отправка сообщения электронной почты с маркеров в тексте сообщения.</span><span class="sxs-lookup"><span data-stu-id="a36aa-178">This code snippet demonstrates how you can send email with tokens in the body.</span></span> <span data-ttu-id="a36aa-179">Обратите внимание на то, как маркеры включены в текст сообщения.</span><span class="sxs-lookup"><span data-stu-id="a36aa-179">Notice how the tokens are provided in the body property.</span></span> <span data-ttu-id="a36aa-180">Значения для этих маркеров предоставлены для свойства маркеров.</span><span class="sxs-lookup"><span data-stu-id="a36aa-180">Values for those tokens are provided to the tokens property.</span></span>  
  
```csharp  
IDictionary<string, string> tokens = new Dictionary<string, string>();  
tokens.Add("@name", "John Doe");  
tokens.Add("@date", DateTime.Now.ToString());  
tokens.Add("@server", "localhost");  
  
new SendMail  
{  
    From = new LambdaValue<MailAddress>(ctx => new MailAddress("john.doe@contoso.com")),  
    To = new LambdaValue<MailAddressCollection>(  
                    ctx => new MailAddressCollection() { new MailAddress("someone@microsoft.com") }),  
    Subject = "Test email",  
    Body = "Hello @name. This is a test email sent from @server. Current date is @date",  
    Host = "localhost",  
    Port = 25,  
    Tokens = new LambdaValue<IDictionary<string, string>>(ctx => tokens)  
};  
```  
  
### <a name="sending-an-email-using-a-template"></a><span data-ttu-id="a36aa-181">Отправка сообщения электронной почты с использованием шаблона</span><span class="sxs-lookup"><span data-stu-id="a36aa-181">Sending an email using a template</span></span>  
 <span data-ttu-id="a36aa-182">В этом фрагменте описывается отправка сообщения электронной почты с использованием маркеров шаблона в тексте.</span><span class="sxs-lookup"><span data-stu-id="a36aa-182">This snippet shows how to send an email using a template tokens in the body.</span></span> <span data-ttu-id="a36aa-183">Обратите внимание, что при задании свойства `BodyTemplateFilePath` не нужно указывать значение для свойства Body (содержимое файла шаблона будет скопировано в текст).</span><span class="sxs-lookup"><span data-stu-id="a36aa-183">Notice that when setting the `BodyTemplateFilePath` property we don’t need to provide the value for Body property (the contents of the template file will be copied to the body).</span></span>  
  
```csharp  
new SendMail  
{
    From = new LambdaValue<MailAddress>(ctx => new MailAddress("john.doe@contoso.com")),  
    To = new LambdaValue<MailAddressCollection>(  
                    ctx => new MailAddressCollection() { new MailAddress("someone@microsoft.com") }),  
    Subject = "Test email",  
    Host = "localhost",  
    Port = 25,  
    Tokens = new LambdaValue<IDictionary<string, string>>(ctx => tokens),  
    BodyTemplateFilePath = @"..\..\..\SendMail\Templates\MailTemplateBody.htm",
};  
```  
  
### <a name="sending-mails-in-testing-mode"></a><span data-ttu-id="a36aa-184">Отправка сообщений в тестовом режиме</span><span class="sxs-lookup"><span data-stu-id="a36aa-184">Sending Mails in Testing Mode</span></span>  
 <span data-ttu-id="a36aa-185">На этом фрагменте кода показано, как установить `TestMailTo` два свойства тестирования: при установке всех сообщений будет отправлено `john.doe@contoso.con` (без учета значений To, Cc, Bcc).</span><span class="sxs-lookup"><span data-stu-id="a36aa-185">This code snippet shows how to set the two testing properties: by setting `TestMailTo` to all messages will be sent to `john.doe@contoso.con` (without regard of the values of To, Cc, Bcc).</span></span> <span data-ttu-id="a36aa-186">При задании TestDropPath все исходящие сообщения электронной почты будут также записываться по указанному пути.</span><span class="sxs-lookup"><span data-stu-id="a36aa-186">By setting TestDropPath all outgoing emails will be also recorded in the provided path.</span></span> <span data-ttu-id="a36aa-187">Эти свойства могут быть заданы независимо (они не связаны друг с другом).</span><span class="sxs-lookup"><span data-stu-id="a36aa-187">These properties can be set independently (they are not related).</span></span>  
  
```csharp  
new SendMail  
{
   From = new LambdaValue<MailAddress>(ctx => new MailAddress("john.doe@contoso.com")),  
   To = new LambdaValue<MailAddressCollection>(  
                    ctx => new MailAddressCollection() { new MailAddress("someone@microsoft.com") }),  
   Subject = "Test email",  
   Host = "localhost",  
   Port = 25,  
   Tokens = new LambdaValue<IDictionary<string, string>>(ctx => tokens),  
   BodyTemplateFilePath = @"..\..\..\SendMail\Templates\MailTemplateBody.htm",  
   TestMailTo= new LambdaValue<MailAddress>(ctx => new MailAddress("john.doe@contoso.com")),  
   TestDropPath = @"c:\Samples\SendMail\TestDropPath\",  
};  
```  
  
## <a name="set-up-instructions"></a><span data-ttu-id="a36aa-188">Инструкции по установке</span><span class="sxs-lookup"><span data-stu-id="a36aa-188">Set-Up Instructions</span></span>  
 <span data-ttu-id="a36aa-189">В этом образце необходим доступ к SMTP-серверу.</span><span class="sxs-lookup"><span data-stu-id="a36aa-189">Access to a SMTP server is required for this sample.</span></span>  
  
 <span data-ttu-id="a36aa-190">Для получения дополнительной информации о настройке сервера SMTP см.</span><span class="sxs-lookup"><span data-stu-id="a36aa-190">For more information about setting up a SMTP server, see the following links.</span></span>  
  
- <span data-ttu-id="a36aa-191">[Настройка службы SMTP (IIS 6.0)](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2003/cc784968(v=ws.10))</span><span class="sxs-lookup"><span data-stu-id="a36aa-191">[Configuring the SMTP Service (IIS 6.0)](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2003/cc784968(v=ws.10))</span></span>  
  
- <span data-ttu-id="a36aa-192">[IIS 7.0: настройка протокола электронной почты SMTP](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc772058(v=ws.10))</span><span class="sxs-lookup"><span data-stu-id="a36aa-192">[IIS 7.0: Configure SMTP E-Mail](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc772058(v=ws.10))</span></span>  
  
- <span data-ttu-id="a36aa-193">[Установка службы SMTP](https://docs.microsoft.com/previous-versions/tn-archive/aa997480(v=exchg.65))</span><span class="sxs-lookup"><span data-stu-id="a36aa-193">[How to Install the SMTP Service](https://docs.microsoft.com/previous-versions/tn-archive/aa997480(v=exchg.65))</span></span>  
  
 <span data-ttu-id="a36aa-194">Эмуляторы SMTP разработки сторонних производителей можно загрузить из Интернета.</span><span class="sxs-lookup"><span data-stu-id="a36aa-194">SMTP emulators provided by third parties are available for download.</span></span>  
  
##### <a name="to-run-this-sample"></a><span data-ttu-id="a36aa-195">Запуск образца</span><span class="sxs-lookup"><span data-stu-id="a36aa-195">To run this sample</span></span>  
  
1. <span data-ttu-id="a36aa-196">Используя Visual Studio 2010, откройте файл решения SendMail.sln.</span><span class="sxs-lookup"><span data-stu-id="a36aa-196">Using Visual Studio 2010, open the SendMail.sln solution file.</span></span>  
  
2. <span data-ttu-id="a36aa-197">Убедитесь, что имеется доступ к работающему SMTP-серверу.</span><span class="sxs-lookup"><span data-stu-id="a36aa-197">Ensure that you have access to a valid SMTP server.</span></span> <span data-ttu-id="a36aa-198">См. инструкции по настройке.</span><span class="sxs-lookup"><span data-stu-id="a36aa-198">See the set-up instructions.</span></span>  
  
3. <span data-ttu-id="a36aa-199">Назначьте программу с помощью адреса сервера, а также адреса электронной почты From and To.</span><span class="sxs-lookup"><span data-stu-id="a36aa-199">Configure the program with your server address, and From and To email addresses.</span></span>  
  
     <span data-ttu-id="a36aa-200">Чтобы правильно выполнить этот образец, может потребоваться настроить значение адресов электронной почты from and To и адреса сервера SMTP в Program.cs и в Sequence.xaml.</span><span class="sxs-lookup"><span data-stu-id="a36aa-200">To correctly run this sample, you may need to configure the value of From and To email addresses and the address of the SMTP server in  Program.cs and in Sequence.xaml.</span></span> <span data-ttu-id="a36aa-201">Потребуется изменение адреса в обоих расположениях, поскольку программа отправляет сообщения двумя различными способами</span><span class="sxs-lookup"><span data-stu-id="a36aa-201">You will need to change the address in both locations since the program sends mail in two different ways</span></span>  
  
4. <span data-ttu-id="a36aa-202">Для построения решения нажмите CTRL+SHIFT+B.</span><span class="sxs-lookup"><span data-stu-id="a36aa-202">To build the solution, press CTRL+SHIFT+B.</span></span>  
  
5. <span data-ttu-id="a36aa-203">Чтобы запустить решение, нажмите клавиши CTRL+F5.</span><span class="sxs-lookup"><span data-stu-id="a36aa-203">To run the solution, press CTRL+F5.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="a36aa-204">Образцы уже могут быть установлены на компьютере.</span><span class="sxs-lookup"><span data-stu-id="a36aa-204">The samples may already be installed on your machine.</span></span> <span data-ttu-id="a36aa-205">Перед продолжением проверьте следующий каталог (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="a36aa-205">Check for the following (default) directory before continuing.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> <span data-ttu-id="a36aa-206">Если этого каталога не существует, перейдите в [Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) Образцы для .NET Framework 4,](https://www.microsoft.com/download/details.aspx?id=21459) чтобы загрузить все Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] образцы.</span><span class="sxs-lookup"><span data-stu-id="a36aa-206">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="a36aa-207">Этот образец расположен в следующем каталоге.</span><span class="sxs-lookup"><span data-stu-id="a36aa-207">This sample is located in the following directory.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\ActivityLibrary\SendMail`
