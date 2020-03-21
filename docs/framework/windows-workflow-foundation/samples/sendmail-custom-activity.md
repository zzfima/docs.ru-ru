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
# <a name="sendmail-custom-activity"></a>Настраиваемое действие SendMail
В образце описывается создание настраиваемого действия, которое является производным от <xref:System.Activities.AsyncCodeActivity>, для отправки почты с помощью SMTP для работы в приложении рабочего процесса. Пользовательская деятельность использует <xref:System.Net.Mail.SmtpClient> возможности для асинхронного отправки электронной почты и отправки почты с аутентификацией. При этом также обеспечивается возможность использования таких возможностей конечных пользователей, как тестовый режим, замена маркеров, шаблоны файлов и тестовый путь размещения файла.  
  
 В следующей таблице представлены аргументы для действия `SendMail`.  
  
|Имя|Тип|Описание|  
|-|-|-|  
|Узел|Строка|Адрес узла SMTP-сервера.|  
|Порт|Строка|Порт службы SMTP на узле.|  
|EnableSsl|bool|Указывает, использует ли <xref:System.Net.Mail.SmtpClient> протокол SSL для шифрования соединения.|  
|UserName|Строка|Имя пользователя для настройки учетных данных для проверки подлинности свойства <xref:System.Net.Mail.SmtpClient.Credentials%2A> отправителя.|  
|Пароль|Строка|Пароль для настройки учетных данных для проверки подлинности свойства <xref:System.Net.Mail.SmtpClient.Credentials%2A> отправителя.|  
|Тема|<xref:System.Activities.InArgument%601>\<струнная>|Тема сообщения.|  
|Текст|<xref:System.Activities.InArgument%601>\<струнная>|Текст сообщения.|  
|Вложения|<xref:System.Activities.InArgument%601>\<струнная>|Сбор приложений, используемый для хранения данных, прикрепленных к этому сообщению электронной почты.|  
|От|<xref:System.Net.Mail.MailAddress>|С адреса для этого сообщения электронной почты.|  
|Чтобы|<xref:System.Activities.InArgument%601>\<<xref:System.Net.Mail.MailAddressCollection>>|Коллекция адресов, содержащая получателей этого сообщения электронной почты.|  
|CC|<xref:System.Activities.InArgument%601>\<<xref:System.Net.Mail.MailAddressCollection>>|Коллекция адресов, содержащая получателей копии углерода (CC) для этого сообщения электронной почты.|  
|BCC|<xref:System.Activities.InArgument%601>\<<xref:System.Net.Mail.MailAddressCollection>>|Коллекция адресов, содержащая получателей слепой копии углерода (BCC) для этого сообщения электронной почты.|  
|Токены|<xref:System.Activities.InArgument%601><строка\<IDictionary, струнная>>|Маркеры для замены в тексте. Эта возможность позволяет пользователям указывать определенные значением в тексте сообщения, которые можно позднее заменить маркерами, предоставляемыми при использовании этого свойства.|  
|BodyTemplateFilePath|Строка|Путь к шаблону текста. Действие `SendMail` копирует содержимое этого файла в свойство текста.<br /><br /> Этот шаблон может содержать токены, которые заменяются на содержимое свойства Tokens.|  
|TestMailTo|<xref:System.Net.Mail.MailAddress>|Когда это свойство установлено, все электронные письма отправляются на указанный в нем адрес.<br /><br /> Это свойство планируется использовать при тестировании рабочих процессов. Например, если вы хотите убедиться, что все письма отправляются без отправки их фактическим получателям.|  
|TestDropPath|Строка|Когда это свойство установлено, все сообщения электронной почты также сохраняются в указанном файле.<br /><br /> Это свойство предназначено для использования при тестировании или отладке рабочих процессов, чтобы убедиться, что формат и содержимые письма является подходящим.|  
  
## <a name="solution-contents"></a>Содержимое решения  
 Решение содержит два проекта.  
  
|Проект|Описание|Важные файлы|  
|-------------|-----------------|---------------------|  
|SendMail|Действие SendMail|1. SendMail.cs: реализация для основного мероприятия<br />2. SendMailDesigner.xaml и SendMailDesigner.xaml.cs: конструктор для деятельности SendMail<br />3. MailTemplateBody.htm: шаблон для электронной почты, которая будет отправлена.|  
|SendMailTestClient|Клиент для тестирования действий SendMail.  В этом проекте описываются два способа вызова действия SendMail: декларативно и программно.|1. Sequence1.xaml: рабочий процесс, который вызывает активность SendMail.<br />2. Program.cs: вызывает Sequence1, а также создает рабочий процесс программно, который использует SendMail.|  
  
## <a name="further-configuration-of-the-sendmail-activity"></a>Дополнительная настройка действия SendMail  
 Хотя она не показана в образце, пользователи могут выполнять дополнительную настройку действия SendMail. Эта дополнительная настройка описывается в следующих трех разделах.  
  
### <a name="sending-an-email-using-tokens-specified-in-the-body"></a>Отправка сообщения электронной почты с использованием маркеров, указанных в тексте сообщения  
 В этом фрагменте кода описывается отправка сообщения электронной почты с маркеров в тексте сообщения. Обратите внимание на то, как маркеры включены в текст сообщения. Значения для этих маркеров предоставлены для свойства маркеров.  
  
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
  
### <a name="sending-an-email-using-a-template"></a>Отправка сообщения электронной почты с использованием шаблона  
 В этом фрагменте описывается отправка сообщения электронной почты с использованием маркеров шаблона в тексте. Обратите внимание, что при задании свойства `BodyTemplateFilePath` не нужно указывать значение для свойства Body (содержимое файла шаблона будет скопировано в текст).  
  
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
  
### <a name="sending-mails-in-testing-mode"></a>Отправка сообщений в тестовом режиме  
 На этом фрагменте кода показано, как установить `TestMailTo` два свойства тестирования: при установке всех сообщений будет отправлено `john.doe@contoso.con` (без учета значений To, Cc, Bcc). При задании TestDropPath все исходящие сообщения электронной почты будут также записываться по указанному пути. Эти свойства могут быть заданы независимо (они не связаны друг с другом).  
  
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
  
## <a name="set-up-instructions"></a>Инструкции по установке  
 В этом образце необходим доступ к SMTP-серверу.  
  
 Для получения дополнительной информации о настройке сервера SMTP см.  
  
- [Настройка службы SMTP (IIS 6.0)](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2003/cc784968(v=ws.10))  
  
- [IIS 7.0: настройка протокола электронной почты SMTP](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc772058(v=ws.10))  
  
- [Установка службы SMTP](https://docs.microsoft.com/previous-versions/tn-archive/aa997480(v=exchg.65))  
  
 Эмуляторы SMTP разработки сторонних производителей можно загрузить из Интернета.  
  
##### <a name="to-run-this-sample"></a>Запуск образца  
  
1. Используя Visual Studio 2010, откройте файл решения SendMail.sln.  
  
2. Убедитесь, что имеется доступ к работающему SMTP-серверу. См. инструкции по настройке.  
  
3. Назначьте программу с помощью адреса сервера, а также адреса электронной почты From and To.  
  
     Чтобы правильно выполнить этот образец, может потребоваться настроить значение адресов электронной почты from and To и адреса сервера SMTP в Program.cs и в Sequence.xaml. Потребуется изменение адреса в обоих расположениях, поскольку программа отправляет сообщения двумя различными способами  
  
4. Для построения решения нажмите CTRL+SHIFT+B.  
  
5. Чтобы запустить решение, нажмите клавиши CTRL+F5.  
  
> [!IMPORTANT]
> Образцы уже могут быть установлены на компьютере. Перед продолжением проверьте следующий каталог (по умолчанию).  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> Если этого каталога не существует, перейдите в [Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) Образцы для .NET Framework 4,](https://www.microsoft.com/download/details.aspx?id=21459) чтобы загрузить все Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] образцы. Этот образец расположен в следующем каталоге.  
>
> `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\ActivityLibrary\SendMail`
