---
title: Олицетворение клиента
ms.date: 03/30/2017
helpviewer_keywords:
- service behaviors, impersonation sample
- Impersonating the Client Sample [Windows Communication Foundation]
- impersonation, Windows Communication Foundation sample
ms.assetid: 8bd974e1-90db-4152-95a3-1d4b1a7734f8
ms.openlocfilehash: 10a8d243b3f053879f183864e955d9260c07865b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79183611"
---
# <a name="impersonating-the-client"></a>Олицетворение клиента
Пример олицетворения демонстрирует, как олицетворять приложение абонента в службе таким образом, чтобы служба могла получить доступ к ресурсам системы от лица абонента.  
  
 Этот образец основан на примере [Self-Host.](../../../../docs/framework/wcf/samples/self-host.md) Файлы конфигурации службы и клиентской конфигурации такие же, как и в образце [Self-Host.](../../../../docs/framework/wcf/samples/self-host.md)  
  
> [!NOTE]
> Процедура настройки и инструкции по построению для данного образца приведены в конце этого раздела.  
  
 Код службы был изменен таким образом, чтобы метод `Add` службы олицетворял абонента с помощью атрибута <xref:System.ServiceModel.OperationBehaviorAttribute>, как показано в следующем примере кода.  
  
```csharp
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
  
```csharp
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
  
```csharp
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
  
 Обратите внимание, что в данном случае абонент не олицетворяется для всего звонка, а только для его части. В общем, олицетворение небольшой части операции предпочтительнее, чем олицетворение всей операции.  
  
 Другие методы не олицетворяют абонента.  
  
 Клиентский код изменен, чтобы уровень олицетворения был установлен в значение <xref:System.Security.Principal.TokenImpersonationLevel.Impersonation>. Клиент задает уровень олицетворения, который будет использоваться службой с помощью перечисления <xref:System.Security.Principal.TokenImpersonationLevel>. Перечисление поддерживает следующие значения: <xref:System.Security.Principal.TokenImpersonationLevel.None>, <xref:System.Security.Principal.TokenImpersonationLevel.Anonymous>, <xref:System.Security.Principal.TokenImpersonationLevel.Identification>, <xref:System.Security.Principal.TokenImpersonationLevel.Impersonation> и <xref:System.Security.Principal.TokenImpersonationLevel.Delegation>. Чтобы выполнить проверку доступа при получении доступа к ресурсу системы на локальном компьютере, защищенном с помощью Windows ACL, уровень олицетворения должен быть установлен в значение <xref:System.Security.Principal.TokenImpersonationLevel.Impersonation>, как показано в следующем примере кода.  
  
```csharp
// Create a client with given client endpoint configuration  
CalculatorClient client = new CalculatorClient();  
  
client.ClientCredentials.Windows.AllowedImpersonationLevel = TokenImpersonationLevel.Impersonation;  
```  
  
 При запуске данного примера запросы и ответы операций отображаются в окнах консоли как службы, так и клиента. Нажмите клавишу ВВОД в каждом окне консоли, чтобы закрыть службу и клиент.  
  
> [!NOTE]
> Служба должна либо работать под административным счетом, либо учетная `http://localhost:8000/ServiceModelSamples` запись, под которым она работает, должна быть предоставлена права на регистрацию URI с слоем HTTP. Такие права могут быть предоставлены путем создания [резервации Namespace](/windows/win32/http/namespace-reservations-registrations-and-routing) с помощью [инструмента Httpcfg.exe.](/windows/win32/http/httpcfg-exe)  
  
> [!NOTE]
> На компьютерах под управлением Windows Server 2003 олицетворение поддерживается только в том случае, если приложение Host.exe имеет привилегию олицетворения. (По умолчанию только администраторы имеют это разрешение.) Чтобы добавить эту привилегию в учетную запись службы работает как, перейдите на **административные инструменты**, открыть **местные политики безопасности**, открыть **локальные политики**, нажмите **назначение прав пользователей**, и выберите **Олицетворение клиента после аутентификации** и дважды нажмите **Свойства,** чтобы добавить пользователя или группу.  
  
### <a name="to-set-up-build-and-run-the-sample"></a>Настройка, сборка и выполнение образца  
  
1. Убедитесь, что вы выполнили [одноразовую процедуру настройки для образцов Фонда связи Windows.](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)  
  
2. Чтобы создать выпуск решения на языке C# или Visual Basic .NET, следуйте инструкциям в разделе [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
3. Чтобы запустить образец в одно- или кросс-машинной конфигурации, следуйте инструкциям в [Запуске образцов Фонда связи Windows.](../../../../docs/framework/wcf/samples/running-the-samples.md)  
  
4. Для демонстрации олицетворения абонента службой, запустите клиент под другой учетной записью, отличной от той, под которой работает служба. Чтобы сделать это, введите в командной строке следующую команду.  
  
    ```console  
    runas /user:<machine-name>\<user-name> client.exe  
    ```  
  
     После этого будет запрошен ввод пароля. Введите пароль для ранее указанной учетной записи.  
  
5. При запуске клиента обратите внимание, что идентификация до и после его запуска будет иметь разные учетные данные.  
