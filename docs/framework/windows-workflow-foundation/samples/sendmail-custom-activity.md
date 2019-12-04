---
title: Настраиваемое действие SendMail
ms.date: 03/30/2017
ms.assetid: 947a9ae6-379c-43a3-9cd5-87f573a5739f
ms.openlocfilehash: b1e2d58a09362569d4d408f6e1c9e589aa6bda76
ms.sourcegitcommit: 5fb5b6520b06d7f5e6131ec2ad854da302a28f2e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/03/2019
ms.locfileid: "74715582"
---
# <a name="sendmail-custom-activity"></a>Настраиваемое действие SendMail
В образце описывается создание настраиваемого действия, которое является производным от <xref:System.Activities.AsyncCodeActivity>, для отправки почты с помощью SMTP для работы в приложении рабочего процесса. Настраиваемое действие использует возможности <xref:System.Net.Mail.SmtpClient> для асинхронной отправки электронной почты и отправки почты с проверкой подлинности. При этом также обеспечивается возможность использования таких возможностей конечных пользователей, как тестовый режим, замена маркеров, шаблоны файлов и тестовый путь размещения файла.  
  
 В следующей таблице представлены аргументы для действия `SendMail`.  
  
|Name|Тип|Описание|  
|-|-|-|  
|Host|Строковое|Адрес узла SMTP-сервера.|  
|Port|Строковое|Порт службы SMTP на узле.|  
|EnableSsl|bool|Указывает, использует ли <xref:System.Net.Mail.SmtpClient> протокол SSL для шифрования соединения.|  
|UserName|Строковое|Имя пользователя для настройки учетных данных для проверки подлинности свойства <xref:System.Net.Mail.SmtpClient.Credentials%2A> отправителя.|  
|Password|Строковое|Пароль для настройки учетных данных для проверки подлинности свойства <xref:System.Net.Mail.SmtpClient.Credentials%2A> отправителя.|  
|Subject|<xref:System.Activities.InArgument%601>строки \<|Тема сообщения.|  
|Текст|<xref:System.Activities.InArgument%601>строки \<|Текст сообщения.|  
|Вложения|<xref:System.Activities.InArgument%601>строки \<|Коллекция вложений, используемая для хранения данных, вложенных в это сообщение электронной почты.|  
|На|<xref:System.Net.Mail.MailAddress>|Адрес для этого сообщения электронной почты.|  
|Чтобы|<xref:System.Activities.InArgument%601>\<<xref:System.Net.Mail.MailAddressCollection>>|Коллекция адресов, содержащая получателей данного сообщения электронной почты.|  
|CC|<xref:System.Activities.InArgument%601>\<<xref:System.Net.Mail.MailAddressCollection>>|Коллекция адресов, содержащая получателей копии (CC) для данного сообщения электронной почты.|  
|BCC|<xref:System.Activities.InArgument%601>\<<xref:System.Net.Mail.MailAddressCollection>>|Коллекция адресов, содержащая получателей скрытой копии (BCC) для данного сообщения электронной почты.|  
|лексемы|<xref:System.Activities.InArgument%601>< IDictionary\<строка, строка > >|Маркеры для замены в тексте. Эта возможность позволяет пользователям указывать определенные значением в тексте сообщения, которые можно позднее заменить маркерами, предоставляемыми при использовании этого свойства.|  
|BodyTemplateFilePath|Строковое|Путь к шаблону текста. Действие `SendMail` копирует содержимое этого файла в свойство текста.<br /><br /> Этот шаблон может содержать токены, которые заменяются на содержимое свойства Tokens.|  
|TestMailTo|<xref:System.Net.Mail.MailAddress>|Если это свойство задано, все сообщения электронной почты отправляются по адресу, указанному в нем.<br /><br /> Это свойство планируется использовать при тестировании рабочих процессов. Например, если нужно убедиться, что все сообщения электронной почты отправляются без отправки их реальным получателям.|  
|TestDropPath|Строковое|Если это свойство задано, все сообщения электронной почты также сохраняются в указанном файле.<br /><br /> Это свойство предназначено для использования при тестировании или отладке рабочих процессов, чтобы убедиться в правильности формата и содержимого исходящих сообщений электронной почты.|  
  
## <a name="solution-contents"></a>Содержимое решения  
 Решение содержит два проекта.  
  
|Проект служб   .|Описание|Важные файлы|  
|-------------|-----------------|---------------------|  
|SendMail|Действие SendMail|1. SendMail.cs: реализация для основного действия<br />2. Сендмаилдесигнер. XAML и SendMailDesigner.xaml.cs: конструктор для действия SendMail<br />3. Маилтемплатебоди. htm: шаблон для отправляемого сообщения электронной почты.|  
|SendMailTestClient|Клиент для тестирования действий SendMail.  В этом проекте описываются два способа вызова действия SendMail: декларативно и программно.|1. Sequence1. XAML: рабочий процесс, вызывающий действие SendMail.<br />2. Program.cs: вызывает Sequence1, а также создает рабочий процесс программным способом, использующим SendMail.|  
  
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
 В этом фрагменте кода показано, как задать два свойства тестирования: при установке `TestMailTo` все сообщения будут отправляться в `john.doe@contoso.con` (без учета значений to, CC, BCC). При задании TestDropPath все исходящие сообщения электронной почты будут также записываться по указанному пути. Эти свойства могут быть заданы независимо (они не связаны друг с другом).  
  
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
  
 Дополнительные сведения о настройке SMTP-сервера см. по следующим ссылкам.  
  
- [Microsoft TechNet](https://go.microsoft.com/fwlink/?LinkId=166060)  
  
- [Настройка службы SMTP (IIS 6,0)](https://go.microsoft.com/fwlink/?LinkId=150456)  
  
- [IIS 7,0: Настройка электронной почты SMTP](https://go.microsoft.com/fwlink/?LinkId=150457)  
  
- [Установка службы SMTP](https://go.microsoft.com/fwlink/?LinkId=150458)  
  
 Эмуляторы SMTP разработки сторонних производителей можно загрузить из Интернета.  
  
##### <a name="to-run-this-sample"></a>Запуск образца  
  
1. Откройте в Visual Studio 2010 файл решения SendMail. sln.  
  
2. Убедитесь, что имеется доступ к работающему SMTP-серверу. См. инструкции по настройке.  
  
3. Настройте программу, указав адрес сервера, а также адреса электронной почты и.  
  
     Для правильного выполнения этого примера может потребоваться настроить значение в адресах электронной почты и адресе SMTP-сервера в Program.cs и в последовательности. XAML. Потребуется изменение адреса в обоих расположениях, поскольку программа отправляет сообщения двумя различными способами  
  
4. Для построения решения нажмите CTRL+SHIFT+B.  
  
5. Чтобы запустить решение, нажмите клавиши CTRL+F5.  
  
> [!IMPORTANT]
> Образцы уже могут быть установлены на компьютере. Перед продолжением проверьте следующий каталог (по умолчанию).  
>   
> `<InstallDrive>:\WF_WCF_Samples`  
>   
> Если этот каталог не существует, перейдите к [примерам Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) для .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) , чтобы скачать все Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Samples. Этот образец расположен в следующем каталоге.  
>   
> `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\ActivityLibrary\SendMail`
