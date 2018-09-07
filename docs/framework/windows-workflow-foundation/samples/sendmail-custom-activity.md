---
title: Настраиваемое действие SendMail
ms.date: 03/30/2017
ms.assetid: 947a9ae6-379c-43a3-9cd5-87f573a5739f
ms.openlocfilehash: e9d27711754c3aa8ff7f68c23f528c9f5c4356f7
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2018
ms.locfileid: "44070528"
---
# <a name="sendmail-custom-activity"></a>Настраиваемое действие SendMail
В образце описывается создание настраиваемого действия, которое является производным от <xref:System.Activities.AsyncCodeActivity>, для отправки почты с помощью SMTP для работы в приложении рабочего процесса. Настраиваемое действие использует возможности <xref:System.Net.Mail.SmtpClient> асинхронно отправлять электронную почту и для отправки почты с проверкой подлинности. При этом также обеспечивается возможность использования таких возможностей конечных пользователей, как тестовый режим, замена маркеров, шаблоны файлов и тестовый путь размещения файла.  
  
 В следующей таблице представлены аргументы для действия `SendMail`.  
  
|Имя|Тип|Описание|  
|-|-|-|  
|Основное приложение|Строковое|Адрес узла SMTP-сервера.|  
|Port|Строковое|Порт службы SMTP на узле.|  
|EnableSsl|bool|Указывает, использует ли <xref:System.Net.Mail.SmtpClient> протокол SSL для шифрования соединения.|  
|UserName|Строковое|Имя пользователя для настройки учетных данных для проверки подлинности свойства <xref:System.Net.Mail.SmtpClient.Credentials%2A> отправителя.|  
|Пароль|Строковое|Пароль для настройки учетных данных для проверки подлинности свойства <xref:System.Net.Mail.SmtpClient.Credentials%2A> отправителя.|  
|Субъект|<xref:System.Activities.InArgument%601>\<строка >|Тема сообщения.|  
|Текст|<xref:System.Activities.InArgument%601>\<строка >|Текст сообщения.|  
|Вложения|<xref:System.Activities.InArgument%601>\<строка >|Коллекцию вложений, используемую для хранения данных, вложенных в это сообщение электронной почты.|  
|Исходный тип|<xref:System.Net.Mail.MailAddress>|Адрес отправителя для данного сообщения электронной почты.|  
|Кому|<xref:System.Activities.InArgument%601>\<<xref:System.Net.Mail.MailAddressCollection>>|Коллекцию адресов, содержащую получателей данного сообщения электронной почты.|  
|CC|<xref:System.Activities.InArgument%601>\<<xref:System.Net.Mail.MailAddressCollection>>|Коллекция, содержащую получателей скрытой копии (CC) данного сообщения электронной почты адресов.|  
|BCC|<xref:System.Activities.InArgument%601>\<<xref:System.Net.Mail.MailAddressCollection>>|Коллекцию адресов, содержащую получателей скрытой копии (BCC) данного сообщения электронной почты.|  
|лексемы|<xref:System.Activities.InArgument%601>< IDictionary\<строка, строка >>|Маркеры для замены в тексте. Эта функция позволяет пользователям указывать определенные значением в тексте сообщения, которые можно позднее заменить маркерами, предоставляемыми при использовании этого свойства.|  
|BodyTemplateFilePath|Строковое|Путь к шаблону текста. Действие `SendMail` копирует содержимое этого файла в свойство текста.<br /><br /> Этот шаблон может содержать токены, которые заменяются на содержимое свойства Tokens.|  
|TestMailTo|<xref:System.Net.Mail.MailAddress>|Если это свойство имеет значение, все сообщения электронной почты отправляются на адрес, указанный в нем.<br /><br /> Это свойство планируется использовать при тестировании рабочих процессов. Например если вы хотите убедиться, что все сообщения электронной почты отправляются без отправки их фактическое получателям.|  
|TestDropPath|String|Если это свойство имеет значение, все сообщения электронной почты, также сохраняются в указанном файле.<br /><br /> Это свойство предназначено для использования при тестировании или отладке рабочих процессов, чтобы убедиться в том, что подходит формат и содержимое исходящие сообщения электронной почты.|  
  
## <a name="solution-contents"></a>Содержимое решения  
 Решение содержит два проекта.  
  
|Project|Описание|Важные файлы|  
|-------------|-----------------|---------------------|  
|SendMail|Действие SendMail|1.  SendMail.cs: реализация для основных действий<br />2.  SendMailDesigner.xaml и SendMailDesigner.xaml.cs:конструктор для действия SendMail<br />3.  MailTemplateBody.htm: шаблон для исходящих сообщений электронной почты.|  
|SendMailTestClient|Клиент для тестирования действий SendMail.  В этом проекте описываются два способа вызова действия SendMail: декларативно и программно.|1.  Sequence1.xaml: рабочий процесс, вызывающий действие SendMail.<br />2.  Program.cs: вызывает Sequence1, а также программно создает рабочий процесс, который использует SendMail.|  
  
## <a name="further-configuration-of-the-sendmail-activity"></a>Дополнительная настройка действия SendMail  
 Хотя она не показана в образце, пользователи могут выполнять дополнительную настройку действия SendMail. Эта дополнительная настройка описывается в следующих трех разделах.  
  
### <a name="sending-an-email-using-tokens-specified-in-the-body"></a>Отправка сообщения электронной почты с использованием маркеров, указанных в тексте сообщения  
 В этом фрагменте кода описывается отправка сообщения электронной почты с маркеров в тексте сообщения. Обратите внимание на то, как маркеры включены в текст сообщения. Значения для этих маркеров предоставлены для свойства маркеров.  
  
```html  
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
  
```  
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
 В этом фрагменте кода показано задание двух свойств тестирования:, задав `TestMailTo` на все сообщения будут отправляться john.doe@contoso.con (без учета значений, Cc, Bcc). При задании TestDropPath все исходящие сообщения электронной почты будут также записываться по указанному пути. Эти свойства могут быть заданы независимо (они не связаны друг с другом).  
  
```  
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
  
 Дополнительные сведения о настройке SMTP-сервера см. следующие ссылки.  
  
-   [Microsoft Technet](https://go.microsoft.com/fwlink/?LinkId=166060)  
  
-   [Настройка службы SMTP (IIS 6.0)](https://go.microsoft.com/fwlink/?LinkId=150456)  
  
-   [IIS 7.0: Настройка электронной почты SMTP](https://go.microsoft.com/fwlink/?LinkId=150457)  
  
-   [Установка службы SMTP](https://go.microsoft.com/fwlink/?LinkId=150458)  
  
 Эмуляторы SMTP разработки сторонних производителей можно загрузить из Интернета.  
  
##### <a name="to-run-this-sample"></a>Запуск образца  
  
1.  С помощью [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] откройте файл решения SendMail.sln.  
  
2.  Убедитесь, что имеется доступ к работающему SMTP-серверу. См. инструкции по настройке.  
  
3.  Настройте программу, задав адрес сервера, с и на адреса электронной почты.  
  
     Чтобы правильно запустить этот пример, необходимо настроить значение и адреса электронной почты и адрес SMTP-сервера в файле Program.cs и sequence.XAML. Потребуется изменение адреса в обоих расположениях, поскольку программа отправляет сообщения двумя различными способами  
  
4.  Для построения решения нажмите CTRL+SHIFT+B.  
  
5.  Чтобы запустить решение, нажмите клавиши CTRL+F5.  
  
> [!IMPORTANT]
>  Образцы уже могут быть установлены на компьютере. Перед продолжением проверьте следующий каталог (по умолчанию).  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Если этот каталог не существует, перейдите к [Windows Communication Foundation (WCF) и образцы Windows Workflow Foundation (WF) для .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) для загрузки всех Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] примеры. Этот образец расположен в следующем каталоге.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\ActivityLibrary\SendMail`