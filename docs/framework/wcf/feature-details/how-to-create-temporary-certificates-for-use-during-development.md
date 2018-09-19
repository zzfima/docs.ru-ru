---
title: Практическое руководство. Создание временных сертификатов для использования во время разработки
ms.date: 03/30/2017
helpviewer_keywords:
- certificates [WCF], creating temporary certificates
- temporary certificates [WCF]
ms.assetid: bc5f6637-5513-4d27-99bb-51aad7741e4a
ms.openlocfilehash: ca495c23b30144013b8efe22b7bf6f3cf38b16cd
ms.sourcegitcommit: 5bbfe34a9a14e4ccb22367e57b57585c208cf757
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "45969841"
---
# <a name="how-to-create-temporary-certificates-for-use-during-development"></a>Практическое руководство. Создание временных сертификатов для использования во время разработки
При разработке безопасной службы или клиента с помощью Windows Communication Foundation (WCF), часто бывает необходимо предоставить сертификат X.509 для использования в качестве учетных данных. Обычно этот сертификат является частью цепи сертификатов, корневой центр которых находится в хранилище «Доверенные корневые центры сертификации» на компьютере. Наличие цепи сертификатов позволяет ограничить набор сертификатов, корневой центр которых, как правило, принадлежит организации или подразделению. Для эмуляции этого во время разработки можно создать два сертификата, чтобы выполнить требования безопасности. Первый сертификат является самозаверяющим и помещается в хранилище «Доверенные корневые центры сертификации». Второй сертификат создается из первого и помещается как в хранилище «Личное» на локальном компьютере, так и в хранилище «Личное» текущего пользователя. Здесь описаны шаги по созданию этих двух сертификатов с помощью Powershell [New-SelfSignedCertificate)](https://docs.microsoft.com/en-us/powershell/module/pkiclient/new-selfsignedcertificate?view=win10-ps) командлета.  
  
> [!IMPORTANT]
>  Сертификаты, которые создает командлет New-SelfSignedCertificate предоставляются исключительно для тестирования. При развертывании службы или клиента убедитесь, что используется соответствующий сертификат, предоставленный центром сертификации. Это может быть на сервере сертификации Windows Server в вашей организации или третьей стороны.  
>   
>  По умолчанию [New-SelfSignedCertificate](https://docs.microsoft.com/en-us/powershell/module/pkiclient/new-selfsignedcertificate?view=win10-ps) командлет создает самозаверяющие сертификаты, и эти сертификаты сделаны ненадежными. Размещение самозаверяющие сертификаты в доверенных корневых центров сертификации магазина позволяет создать среду разработки, более точно моделирующую среду развертывания.  
  
 Дополнительные сведения о создании и использовании сертификатов см. в разделе [работа с сертификатами](../../../../docs/framework/wcf/feature-details/working-with-certificates.md). Дополнительные сведения об использовании сертификата в качестве учетных данных см. в разделе [Securing Services and Clients](../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md). Руководство по использованию технологии Microsoft Authenticode см. в разделе [и учебникам по Authenticode](https://go.microsoft.com/fwlink/?LinkId=88919).  
  
### <a name="to-create-a-self-signed-root-authority-certificate-and-export-the-private-key"></a>Создание самозаверяющего сертификата корневого центра и экспорт закрытого ключа  
  
Следующая команда создает самозаверяющий сертификат с именем субъекта «RootCA» в хранилище личных текущего пользователя. 
```
PS $rootCert = New-SelfSignedCertificate -CertStoreLocation cert:\CurrentUser\My -DnsName "RootCA" -TextExtension @("1.3.6.1.4.1.311.21.10={text}1.3.6.1.5.5.7.3.1,1.3.6.1.5.5.7.3.2")
```
Нам нужно экспортировать сертификат в PFX-файл, чтобы его можно было импортировать в там, где необходимо в дальнейшем. При экспорте сертификата с закрытым ключом, чтобы защитить ее нужен пароль. Сохранить пароль в `SecureString` и использовать [Export-PfxCertificate](https://docs.microsoft.com/en-us/powershell/module/pkiclient/export-pfxcertificate?view=win10-ps) командлет, чтобы экспортировать сертификат с помощью соответствующего закрытого ключа в PFX-файл. Мы также сохраняем только открытого сертификата в CRT файла [экспорта сертификата](https://docs.microsoft.com/en-us/powershell/module/pkiclient/export-certificate?view=win10-ps) командлета.
```
PS [System.Security.SecureString]$rootcertPassword = ConvertTo-SecureString -String "password" -Force -AsPlainText
PS [String]$rootCertPath = Join-Path -Path 'cert:\CurrentUser\My\' -ChildPath "$($rootcert.Thumbprint)"
PS Export-PfxCertificate -Cert $rootCertPath -FilePath 'RootCA.pfx' -Password $rootcertPassword
PS Export-Certificate -Cert $rootCertPath -FilePath 'RootCA.crt'
```

### <a name="to-create-a-new-certificate-signed-by-a-root-authority-certificate"></a>Создание нового сертификата, подписанного сертификатом корневого центра  
  
Следующая команда создает сертификат, подписанный `RootCA` с именем субъекта «SignedByRootCA» с помощью закрытого ключа издателя.
```
PS $testCert = New-SelfSignedCertificate -CertStoreLocation Cert:\LocalMachine\My -DnsName "SignedByRootCA" -KeyExportPolicy Exportable -KeyLength 2048 -KeyUsage DigitalSignature,KeyEncipherment -Signer $rootCert 
```
Аналогичным образом мы сохраняем подписанный сертификат с закрытым ключом в PFX-файл и открытый ключ в файл CRT.
```
PS [String]$testCertPath = Join-Path -Path 'cert:\LocalMachine\My\' -ChildPath "$($testCert.Thumbprint)"
PS Export-PfxCertificate -Cert $testCertPath -FilePath testcert.pfx -Password $rootcertPassword 
PS Export-Certificate -Cert $testCertPath -FilePath testcert.crt        
```
  
## <a name="installing-a-certificate-in-the-trusted-root-certification-authorities-store"></a>Установка сертификата в хранилище «Доверенные корневые центры сертификации»  
 После создания самозаверяющего сертификата его можно установить в хранилище «Доверенные корневые центры сертификации». Компьютер доверяет любым сертификатам, подписанным этим сертификатом в этой точке. Поэтому удалите сертификат из хранилища, если он больше не требуется. При удалении этого сертификата корневого центра все другие сертификаты, подписанные им, становятся неавторизованными. Сертификаты корневого центра представляют собой лишь механизм, с помощью которого при необходимости можно ограничить группу сертификатов. Например, в одноранговых приложениях обычно нет необходимости использовать корневой центр, поскольку идентификация отдельного элемента просто доверяется в предоставленном с ним сертификате.  
  
#### <a name="to-install-a-self-signed-certificate-in-the-trusted-root-certification-authorities"></a>Установка самозаверяющего сертификата в хранилище «Доверенные корневые центры сертификации»  
  
1.  Откройте оснастку сертификата. (Дополнительные сведения см. в разделе [Практическое руководство. Просмотр сертификатов с помощью оснастки консоли MMC](../../../../docs/framework/wcf/feature-details/how-to-view-certificates-with-the-mmc-snap-in.md).)  
  
2.  Откройте папку, чтобы сохранить сертификат: **Локальный компьютер** либо **Текущий пользователь**.  
  
3.  Откройте папку **Доверенные корневые центры сертификации** .  
  
4.  Щелкните правой кнопкой мыши папку **Сертификаты** , выберите пункт **Все задачи**, а затем выберите **Импортировать**.  
  
5.  Следуйте инструкциям мастера на экране, чтобы импортировать TempCa.cer в хранилище.  
  
## <a name="using-certificates-with-wcf"></a>Использование сертификатов с WCF  
 После настройки временных сертификатов их можно использовать для разработки решений WCF, задающих сертификаты как тип учетных данных клиента. Например, в следующей конфигурации XML в качестве типа учетных данных клиента задается безопасность сообщения и сертификат.  
  
#### <a name="to-specify-a-certificate-as-the-client-credential-type"></a>Задание сертификата как типа учетных данных клиента  
  
-   В файле конфигурации для службы используйте следующий XML, чтобы настроить режим безопасности сообщения и задать тип учетных данных клиента для сертификата.  
  
    ```xml  
    <bindings>       
      <wsHttpBinding>  
        <binding name="CertificateForClient">  
          <security>  
            <message clientCredentialType="Certificate" />  
          </security>  
        </binding>  
      </wsHttpBinding>  
    </bindings>  
    ```  
  
 В файле конфигурации для клиента используйте следующий XML, чтобы указать, что сертификат найден в хранилище и можно найти путем поиска в поле SubjectName для значения «CohoWinery».  
  
```xml  
<behaviors>  
  <endpointBehaviors>  
    <behavior name="CertForClient">  
      <clientCredentials>  
        <clientCertificate findValue="CohoWinery" x509FindType="FindBySubjectName" />  
       </clientCredentials>  
     </behavior>  
   </endpointBehaviors>  
</behaviors>  
```  
  
 Дополнительные сведения об использовании сертификатов в WCF см. в разделе [Working with Certificates](../../../../docs/framework/wcf/feature-details/working-with-certificates.md).  
  
## <a name="net-framework-security"></a>Безопасность платформы .NET Framework  
 Не забудьте удалить любые временные сертификаты корневого центра из папки **Доверенные корневые центры сертификации** и папки **Личное** , щелкнув правой кнопкой мыши сертификат и выбрав **Удалить**.  
  
## <a name="see-also"></a>См. также  
 [Работа с сертификатами](../../../../docs/framework/wcf/feature-details/working-with-certificates.md)  
 [Практическое руководство. Просмотр сертификатов с помощью оснастки консоли MMC](../../../../docs/framework/wcf/feature-details/how-to-view-certificates-with-the-mmc-snap-in.md)  
 [Защита служб и клиентов](../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
