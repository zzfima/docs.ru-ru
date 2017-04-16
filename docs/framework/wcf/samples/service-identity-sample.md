---
title: "Образец идентификации службы | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 79fa8c1c-85bb-4b67-bc67-bfaf721303f8
caps.latest.revision: 24
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 24
---
# Образец идентификации службы
В этом образце удостоверения службы демонстрируется, как назначить удостоверение для службы.Во время проектирования клиент может извлечь удостоверение используя метаданные службы, а затем в среде выполнения клиент может проверить подлинность удостоверения службы.Концепция удостоверения службы позволяет клиенту проверять подлинность службы перед вызовом любых ее операций, защищая таким образом клиента от вызовов, не прошедших проверку подлинности.При безопасном подключении служба также проводит проверку подлинности учетных данных клиента перед тем, как предоставить им доступ. Однако это выходит за рамки данного образца.В разделе [Клиент](../../../../docs/framework/wcf/samples/client.md) см. образцы, которые демонстрируют проверку подлинности сервера.  
  
> [!NOTE]
>  Процедура установки и инструкции по построению для данного образца приведены в конце этого раздела.  
  
 В этом образце демонстрируются следующие функции.  
  
-   Как задать различные типы удостоверения для службы на различных конечных точках.Каждый тип удостоверения обладает различным возможностями.Используемый тип удостоверения зависит от типа учетных данных безопасности, используемых для привязки в конечной точке.  
  
-   Удостоверение может быть задано как декларативно в конфигурации, так и императивно в коде.Обычно используется конфигурация для назначения удостоверения как для клиента, так и для службы.  
  
-   Как назначить пользовательское удостоверение клиенту.Пользовательское удостоверение обычно представляет собой настройку существующего типа удостоверения, которое позволяет клиенту анализировать оставшуюся информацию об утверждениях, передаваемых в учетных данных службы, позволяя принимать решение об авторизации до момента вызова службы.  
  
    > [!NOTE]
    >  Этот образец проверяет удостоверение конкретного сертификата identity.com и ключ RSA, который содержится в этом сертификате.При использовании типов удостоверений Certificate и RSA в конфигурации клиента самый простой способ получить эти значения — проверить WSDL для службы, где эти значения сериализуются.  
  
 В следующем образце кода показано, как сконфигурировать удостоверение конечной точки службы с сервером доменных имен \(DNS\) сертификата, используя WSHttpBinding.  
  
```  
//Create a service endpoint and set its identity to the certificate's DNS                 
WSHttpBinding wsAnonbinding = new WSHttpBinding (SecurityMode.Message);  
// Client are Anonymous to the service  
wsAnonbinding.Security.Message.ClientCredentialType = MessageCredentialType.None;  
WServiceEndpoint ep = serviceHost.AddServiceEndpoint(typeof(ICalculator),wsAnonbinding, String.Empty);  
EndpointAddress epa = new EndpointAddress(dnsrelativeAddress,EndpointIdentity.CreateDnsIdentity("identity.com"));  
ep.Address = epa;  
  
```  
  
 Удостоверение может быть также задано в конфигурации в файле App.config.В следующем примере показано, как задать удостоверение "имя участника\-пользователя" \(UPN\) для конечной точки службы.  
  
```  
<endpoint address="upnidentity"  
        behaviorConfiguration=""  
        binding="wsHttpBinding"  
        bindingConfiguration="WSHttpBinding_Windows"  
        name="WSHttpBinding_ICalculator_Windows"  
        contract="Microsoft.ServiceModel.Samples.ICalculator">  
  <!-- Set the UPN identity for this endpoint -->  
  <identity>  
      <userPrincipalName value="host\myservice.com" />  
  </identity >  
</endpoint>  
  
```  
  
 Пользовательское удостоверение может быть создано на клиенте путем наследования от классов <xref:System.ServiceModel.EndpointIdentity> и <xref:System.ServiceModel.Security.IdentityVerifier>.В принципе, класс <xref:System.ServiceModel.Security.IdentityVerifier> может рассматриваться в качестве клиента, эквивалентного классу службы `AuthorizationManager`.В следующем примере кода показана реализация метода `OrgEndpointIdentity`, хранящего имя организации, которому должно соответствовать имя субъекта сертификата сервера.Авторизация проверяет появление имени организации в методе `CheckAccess` в классе `CustomIdentityVerifier`.  
  
```  
  
// This custom EndpointIdentity stores an organization name   
public class OrgEndpointIdentity : EndpointIdentity  
{  
    private string orgClaim;  
    public OrgEndpointIdentity(string orgName)  
    {  
        orgClaim = orgName;  
    }  
    public string OrganizationClaim  
    {  
        get { return orgClaim; }  
        set { orgClaim = value; }  
    }  
}  
  
//This custom IdentityVerifier uses the supplied OrgEndpointIdentity to  
//check that X.509 certificate's distinguished name claim contains  
//the organization name e.g. the string value "O=Contoso"   
class CustomIdentityVerifier : IdentityVerifier  
{  
    public override bool CheckAccess(EndpointIdentity identity, AuthorizationContext authContext)  
    {  
        bool returnvalue = false;  
        foreach (ClaimSet claimset in authContext.ClaimSets)  
        {  
            foreach (Claim claim in claimset)  
            {  
                if (claim.ClaimType == "http://schemas.microsoft.com/ws/2005/05/identity/claims/x500distinguishedname")  
                {  
                    X500DistinguishedName name = (X500DistinguishedName)claim.Resource;  
                    if (name.Name.Contains(((OrgEndpointIdentity)identity).OrganizationClaim))  
                    {  
                        Console.WriteLine("Claim Type: {0}",claim.ClaimType);  
                        Console.WriteLine("Right: {0}", claim.Right);  
                        Console.WriteLine("Resource: {0}",claim.Resource);  
                        Console.WriteLine();  
                        returnvalue = true;  
                    }  
                }  
            }  
        }  
        return returnvalue;  
    }  
}  
```  
  
 Этот образец использует сертификат identity.com, который находится в соответствующей языковой папке решения для идентификации.  
  
### Настройка, построение и выполнение образца  
  
1.  Убедитесь, что выполнены процедуры, описанные в разделе [Процедура однократной настройки образцов Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).  
  
2.  Чтобы создать выпуск решения на языке C\# или Visual Basic .NET, следуйте инструкциям в разделе [Построение образцов Windows Communication Foundation](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
3.  Чтобы запустить образец на одном или нескольких компьютерах, следуйте инструкциям в разделе [Выполнение примеров Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).  
  
### Запуск образца на одном компьютере  
  
1.  Для операционной системы [!INCLUDE[wxp](../../../../includes/wxp-md.md)] или [!INCLUDE[wv](../../../../includes/wv-md.md)] импортируйте файл сертификата Identity.pfx в папку решения для идентификации в хранилище сертификатов LocalMachine\/My \(Personal\) с помощью средства оснастки MMC.Этот файл защищен паролем.Во время импорта будет запрошен пароль.Введите строку `xyz` в поле ввода пароля.Дополнительные сведения см. в разделе [Как просматривать сертификаты с помощью оснастки консоли MMC](../../../../docs/framework/wcf/feature-details/how-to-view-certificates-with-the-mmc-snap-in.md).После выполнения описанных выше действий запустите из командной строки Visual Studio с правами администратора файл Setup.bat, который копирует этот сертификат в хранилище «CurrentUser\/Trusted People» для использования на клиенте.  
  
2.  На [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)] откройте окно командной строки [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] с правами администратора и запустите файл Setup.bat из папки установки образца.При этом устанавливаются все сертификаты, необходимые для запуска образца.  
  
    > [!NOTE]
    >  Пакетный файл Setup.bat предназначен для запуска из командной строки [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)].Переменная среды PATH, заданная в командной строке [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)], указывает на каталог, содержащий исполняемые файлы, необходимые для скрипта Setup.bat.После завершения работы образца выполните в папке образца файл Cleanup.bat, чтобы удалить сертификаты.В других образцах обеспечения безопасности используются те же сертификаты.  
  
3.  Запустите программу Service.exe из каталога \\service\\bin.Убедитесь, что служба запущена и выводит приглашение к завершению работы службы нажатием клавиши \<ВВОД\>.  
  
4.  Запустите файл Client.exe из каталога \\client\\bin, или нажав F5 в Visual Studio для построения и выполнения примера.Действия клиента отображаются в консольном приложении клиента.  
  
5.  Если клиенту и службе не удается взаимодействовать, см. раздел [Troubleshooting Tips](http://msdn.microsoft.com/ru-ru/8787c877-5e96-42da-8214-fa737a38f10b).  
  
### Запуск образца на нескольких компьютерах  
  
1.  Перед тем как построить клиентскую часть образца, убедитесь в изменении значения адреса конечной точки службы в файле Client.cs в методе `CallServiceCustomClientIdentity`.После этого постройте образец.  
  
2.  Создайте каталог на компьютере службы.  
  
3.  Скопируйте файлы служебной программ из каталога service\\bin в каталог на компьютере службы.Кроме того, скопируйте файлы Setup.bat и Cleanup.bat на компьютер службы.  
  
4.  Создайте на клиентском компьютере каталог для двоичных файлов клиента.  
  
5.  Скопируйте в клиентский каталог на клиентском компьютере файлы программы клиента.Кроме того, скопируйте на клиент файлы Setup.bat, Cleanup.bat и ImportServiceCert.bat.  
  
6.  В службе откройте командную строку Visual Studio с правами администратора и запустите `setup.bat service`.При запуске команды `setup.bat` с аргументом `service` создается сертификат службы с полным именем домена компьютера и экспортируется в файл с именем Service.cer.  
  
7.  Скопируйте файл Service.cer из каталога службы в клиентский каталог на клиентском компьютере.  
  
8.  В файле Client.exe.config на клиентском компьютере измените значение адреса конечной точки, чтобы оно соответствовало новому адресу службы.Есть несколько экземпляров, которые должны быть изменены.  
  
9. На клиентском компьютере откройте командную строку Visual Studio с правами администратора и запустите файл ImportServiceCert.bat.Он импортирует сертификат службы из файла Service.cer в хранилище CurrentUser \- TrustedPeople.  
  
10. На компьютере службы запустите из командной строки программу Service.exe.  
  
11. На клиентском компьютере из командной строки запустите программу Client.exe.Если клиенту и службе не удается взаимодействовать, см. раздел [Troubleshooting Tips](http://msdn.microsoft.com/ru-ru/8787c877-5e96-42da-8214-fa737a38f10b).  
  
### Очистка после образца  
  
-   После завершения работы образца запустите в папке образцов файл Cleanup.bat.  
  
    > [!NOTE]
    >  Этот скрипт не удаляет сертификаты службы на клиенте при запуске образца на нескольких компьютерах.Если образцы [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)], в которых использовались сертификаты, запускались на нескольких компьютерах, обязательно удалите сертификаты службы, которые были установлены в хранилище «CurrentUser — TrustedPeople».Для этого воспользуйтесь следующей командой: `certmgr -del -r CurrentUser -s TrustedPeople -c -n <Fully Qualified Server Machine Name>`. Пример: `certmgr -del -r CurrentUser -s TrustedPeople -c -n server1.contoso.com`.  
  
## См. также