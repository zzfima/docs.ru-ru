---
title: "Олицетворение клиента | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "пример олицетворения клиента [Windows Communication Foundation]"
  - "олицетворение, образец Windows Communication Foundation"
  - "поведения служб, пример олицетворения"
ms.assetid: 8bd974e1-90db-4152-95a3-1d4b1a7734f8
caps.latest.revision: 25
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 25
---
# Олицетворение клиента
Пример олицетворения демонстрирует, как олицетворять приложение абонента в службе таким образом, чтобы служба могла получить доступ к ресурсам системы от лица абонента.  
  
 Этот пример основан на примере [Резидентное размещение](../../../../docs/framework/wcf/samples/self-host.md).Файлы конфигурации службы и клиента такие же, как в примере [Резидентное размещение](../../../../docs/framework/wcf/samples/self-host.md).  
  
> [!NOTE]
>  Процедура настройки и инструкции по построению для данного примера приведены в конце этого раздела.  
  
 Код службы был изменен таким образом, чтобы метод `Add` службы олицетворял абонента с помощью атрибута <xref:System.ServiceModel.OperationBehaviorAttribute>, как показано в следующем примере кода.  
  
```  
[OperationBehavior(Impersonation = ImpersonationOption.Required)]  
public double Add(double n1, double n2)  
{  
    double result = n1 + n2;  
    Console.WriteLine("Received Add({0},{1})", n1, n2);  
    Console.WriteLine("Return: {0}", result);  
    DisplayIdentityInformation();  
    return result;  
}  
  
```  
  
 В результате контекст безопасности выполняющегося потока переключается на олицетворение абонента перед вводом метода `Add` и возврата к выходу из метода.  
  
 Метод `DisplayIdentityInformation`, показанный в следующем примере кода, является служебной функцией, отображающей идентификацию абонента.  
  
```  
static void DisplayIdentityInformation()  
{  
    Console.WriteLine("\t\tThread Identity            :{0}",  
         WindowsIdentity.GetCurrent().Name);  
    Console.WriteLine("\t\tThread Identity level  :{0}",   
         WindowsIdentity.GetCurrent().ImpersonationLevel);  
    Console.WriteLine("\t\thToken                     :{0}",  
         WindowsIdentity.GetCurrent().Token.ToString());  
    return;  
}  
  
```  
  
 Метод `Subtract` службы олицетворяет абонента с помощью принудительных вызовов, как показано в следующем примере кода.  
  
```  
public double Subtract(double n1, double n2)  
{  
    double result = n1 - n2;  
    Console.WriteLine("Received Subtract({0},{1})", n1, n2);  
    Console.WriteLine("Return: {0}", result);  
Console.WriteLine("Before impersonating");  
DisplayIdentityInformation();  
  
    if (ServiceSecurityContext.Current.WindowsIdentity.ImpersonationLevel == TokenImpersonationLevel.Impersonation ||  
        ServiceSecurityContext.Current.WindowsIdentity.ImpersonationLevel == TokenImpersonationLevel.Delegation)  
    {  
        // Impersonate.  
        using (ServiceSecurityContext.Current.WindowsIdentity.Impersonate())  
        {  
            // Make a system call in the caller's context and ACLs   
            // on the system resource are enforced in the caller's context.   
            Console.WriteLine("Impersonating the caller imperatively");  
            DisplayIdentityInformation();  
        }  
    }  
    else  
    {  
        Console.WriteLine("ImpersonationLevel is not high enough to perform this operation.");  
    }  
  
Console.WriteLine("After reverting");  
DisplayIdentityInformation();  
    return result;  
}  
```  
  
 Обратите внимание, что в данном случае абонент не олицетворяется для всего звонка, а только для его части.В общем, олицетворение небольшой части операции предпочтительнее, чем олицетворение всей операции.  
  
 Другие методы не олицетворяют абонента.  
  
 Клиентский код изменен, чтобы уровень олицетворения был установлен в значение <xref:System.Security.Principal.TokenImpersonationLevel>.Клиент задает уровень олицетворения, который будет использоваться службой с помощью перечисления <xref:System.Security.Principal.TokenImpersonationLevel>.Перечисление поддерживает следующие значения: <xref:System.Security.Principal.TokenImpersonationLevel>, <xref:System.Security.Principal.TokenImpersonationLevel>, <xref:System.Security.Principal.TokenImpersonationLevel>, <xref:System.Security.Principal.TokenImpersonationLevel> и <xref:System.Security.Principal.TokenImpersonationLevel>.Чтобы выполнить проверку доступа при получении доступа к ресурсу системы на локальном компьютере, защищенном с помощью Windows ACL, уровень олицетворения должен быть установлен в значение <xref:System.Security.Principal.TokenImpersonationLevel>, как показано в следующем примере кода.  
  
```  
// Create a client with given client endpoint configuration  
CalculatorClient client = new CalculatorClient();  
  
client.ClientCredentials.Windows.AllowedImpersonationLevel = TokenImpersonationLevel.Impersonation;  
```  
  
 При выполнении примера запросы и ответы операций отображаются в окнах консоли как службы, так и клиента.Нажмите клавишу ВВОД в каждом окне консоли, чтобы закрыть службу и клиент.  
  
> [!NOTE]
>  Служба должна быть запущена под учетной записью администратора, или учетная запись, под которой она работает, должна иметь права для регистрации универсального кода ресурса \(URI\) http:\/\/localhost:8000\/ServiceModelSamples с уровнем HTTP.Такие права могут быть даны путем настройки [Резервирования пространства имен](http://go.microsoft.com/fwlink/?LinkId=95012) с помощью [средства Httpcfg.exe](http://go.microsoft.com/fwlink/?LinkId=95010).  
  
> [!NOTE]
>  На компьютерах с [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)] олицетворение поддерживается, только если приложение Host.exe имеет привилегию олицетворения.\(По умолчанию эту привилегию имеют только администраторы\). Для добавления данной привилегии в учетную запись, под которой работает служба, перейдите в **Администрирование**, откройте **Локальная политика безопасности**, откройте **Локальные политики**, щелкните **Назначение прав пользователя** и выберите **Олицетворять клиента после проверки подлинности**, затем дважды щелкните **Свойства** для добавления пользователя или группы.  
  
### Настройка, построение и выполнение примера  
  
1.  Убедитесь, что выполнены процедуры, описанные в разделе [Процедура однократной настройки образцов Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).  
  
2.  Чтобы создать выпуск решения на языке C\# или Visual Basic .NET, следуйте инструкциям в разделе [Построение образцов Windows Communication Foundation](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
3.  Чтобы выполнить пример на одном или нескольких компьютерах, следуйте инструкциям раздела [Выполнение примеров Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).  
  
4.  Для демонстрации олицетворения абонента службой, запустите клиент под другой учетной записью, отличной от той, под которой работает служба.Чтобы сделать это, введите в командной строке следующую команду.  
  
    ```  
    runas /user:<machine-name>\<user-name> client.exe  
    ```  
  
     После этого будет запрошен ввод пароля.Введите пароль для ранее указанной учетной записи.  
  
5.  При запуске клиента обратите внимание, что идентификация до и после его запуска будет иметь разные учетные данные.  
  
## См. также