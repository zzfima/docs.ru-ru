---
title: Безопасность транспорта с обычной проверкой подлинности
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: b54f491d-196b-4279-876c-76b83ec0442c
ms.openlocfilehash: 1b2b451eb1ea6a1a49ce1ba8cc1edef1fe72d01b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79184356"
---
# <a name="transport-security-with-basic-authentication"></a>Безопасность транспорта с обычной проверкой подлинности
На следующей иллюстрации показана служба и клиент Фонда связи Windows (WCF). Серверу требуется действительный сертификат X.509, который можно использовать для протокола SSL, а клиенты должны доверять сертификату сервера. Кроме того, у веб-службы уже имеется сертификат SSL, который можно использовать. Для получения дополнительной информации о возможности базовой <https://docs.microsoft.com/iis/configuration/system.webserver/security/authentication/basicauthentication>аутентификации на Интернет информационных услуг (IIS), см.  
  
 ![Скриншот, который показывает транспортную безопасность с базовой аутентификацией.](./media/transport-security-with-basic-authentication/transport-security-basic-authentication.gif)  
  
|Характеристика|Описание|  
|--------------------|-----------------|  
|Режим безопасности|Транспортировка|  
|Совместимость|С существующими службами и клиентами веб-служб|  
|Проверка подлинности (сервера)<br /><br /> Проверка подлинности (клиента)|Да (по протоколу HTTPS)<br /><br /> Да (по имени/паролю пользователя)|  
|Целостность|Да|  
|Конфиденциальность|Да|  
|Транспортировка|HTTPS|  
|Привязка|<xref:System.ServiceModel.WSHttpBinding>|  
  
## <a name="service"></a>Служба  
 Предполагается, что представленные ниже код и конфигурация выполняются независимо. Выполните одно из следующих действий.  
  
- Создайте автономную службу, используя код без конфигурации.  
  
- Создайте службу, используя предоставленную конфигурацию, но не определяйте конечные точки.  
  
### <a name="code"></a>Код  
 В следующем примере кода показано, как создавать конечную точку службы, использующую имя и пароль пользователя в домене Windows для безопасности передачи. Обратите внимание, что для проверки подлинности клиента службе требуется сертификат X.509. Для получения дополнительной информации [см. Работа с сертификатами](../../../../docs/framework/wcf/feature-details/working-with-certificates.md) и [как: Нанастройка порта с сертификатом SSL](../../../../docs/framework/wcf/feature-details/how-to-configure-a-port-with-an-ssl-certificate.md).  
  
 [!code-csharp[C_SecurityScenarios#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#1)]
 [!code-vb[C_SecurityScenarios#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#1)]  
  
## <a name="configuration"></a>Конфигурация  
 Следующий код служит для настройки службы на использование обычной проверки подлинности с безопасностью на уровне транспорта.  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<configuration>  
    <system.serviceModel>  
        <bindings>  
            <wsHttpBinding>  
                <binding name="UsernameWithTransport">  
                    <security mode="Transport">  
                        <transport clientCredentialType="Basic" />  
                    </security>  
                </binding>  
            </wsHttpBinding>  
        </bindings>  
        <services>  
            <service name="BasicAuthentication.Calculator">  
                <endpoint address="https://localhost/Calculator"  
                          binding="wsHttpBinding"
                          bindingConfiguration="UsernameWithTransport"  
                          name="BasicEndpoint"
                          contract="BasicAuthentication.ICalculator" />  
            </service>  
        </services>  
    </system.serviceModel>  
</configuration>  
```  
  
## <a name="client"></a>клиент  
  
### <a name="code"></a>Код  
 В следующем примере кода демонстрируется код клиента, который содержит имя и пароль пользователя. Обратите внимание, что пользователь должен предоставить действительные имя и пароль пользователя в Windows. В данном разделе не представлен код, возвращающий имя и пароль пользователя. Используйте диалоговое окно или другой интерфейс, чтобы запросить пользователя об этой информации.  
  
> [!NOTE]
> Имя и пароль пользователя задаются только с помощью кода.  
  
 [!code-csharp[C_SecurityScenarios#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#2)]
 [!code-vb[C_SecurityScenarios#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#2)]  
  
### <a name="configuration"></a>Конфигурация  
 В следующем примере кода показана конфигурация клиента.  
  
> [!NOTE]
> Конфигурацию невозможно использовать для задания имени и пароля пользователя. Представленную в этом примере конфигурацию необходимо дополнить с помощью кода, чтобы разрешить задание имени и пароля пользователя.  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<configuration>  
  <system.serviceModel>  
    <bindings>  
      <wsHttpBinding>  
        <binding name="WSHttpBinding_ICalculator" >  
          <security mode="Transport">  
            <transport clientCredentialType="Basic" />  
          </security>  
        </binding>  
      </wsHttpBinding>  
    </bindings>  
    <client>  
      <endpoint address="https://machineName/Calculator"
                binding="wsHttpBinding"  
                bindingConfiguration="WSHttpBinding_ICalculator"
                contract="ICalculator"  
                name="WSHttpBinding_ICalculator" />  
    </client>  
  </system.serviceModel>  
</configuration>  
```  
  
## <a name="see-also"></a>См. также раздел

- <xref:System.ServiceModel.ClientBase%601.ClientCredentials%2A>
- <xref:System.ServiceModel.Security.UserNamePasswordClientCredential>
- [Работа с сертификатами](../../../../docs/framework/wcf/feature-details/working-with-certificates.md)
- [Практическое руководство. Настройка порта с использованием SSL-сертификата](../../../../docs/framework/wcf/feature-details/how-to-configure-a-port-with-an-ssl-certificate.md)
- [Обзор безопасности](../../../../docs/framework/wcf/feature-details/security-overview.md)
- [\<клиентАли>](../../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md)
- [Модель безопасности для Windows Server App Fabric](https://docs.microsoft.com/previous-versions/appfabric/ee677202(v=azure.10))
