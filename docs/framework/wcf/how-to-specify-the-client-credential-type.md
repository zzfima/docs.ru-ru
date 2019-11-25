---
title: Практическое руководство. Указание типа учетных данных клиента
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- security credentials, adding to SOAP messages
- WCF, security
ms.assetid: 10f51bee-5f92-4c1a-9126-fa5418535d8f
ms.openlocfilehash: df18f89ee18bfa33ecc0aced617d168c805e3515
ms.sourcegitcommit: fbb8a593a511ce667992502a3ce6d8f65c594edf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/16/2019
ms.locfileid: "74138574"
---
# <a name="how-to-specify-the-client-credential-type"></a>Практическое руководство. Указание типа учетных данных клиента
После установки режима безопасности (на уровне транспорта или сообщений) можно установить тип учетных данных клиента. Это свойство определяет тип учетных данных, которые клиент должен предоставить службе для проверки подлинности. Дополнительные сведения о настройке режима безопасности (необходимого шага перед настройкой типа учетных данных клиента) см. [в разделе как задать режим безопасности](how-to-set-the-security-mode.md).  
  
### <a name="to-set-the-client-credential-type-in-code"></a>Установка типа учетных данных клиента в коде  
  
1. Создайте экземпляр привязки, который будет использовать служба. В этом примере используется привязка <xref:System.ServiceModel.WSHttpBinding>.  
  
2. Присвойте свойству <xref:System.ServiceModel.WSHttpSecurity.Mode%2A> соответствующее значение. В этом примере используется режим Message.  
  
3. Присвойте свойству <xref:System.ServiceModel.MessageSecurityOverHttp.ClientCredentialType%2A> соответствующее значение. В этом примере используется проверка подлинности Windows (<xref:System.ServiceModel.MessageCredentialType.Windows>).  
  
     [!code-csharp[c_ProgrammingSecurity#14](../../../samples/snippets/csharp/VS_Snippets_CFX/c_programmingsecurity/cs/source.cs#14)]
     [!code-vb[c_ProgrammingSecurity#14](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_programmingsecurity/vb/source.vb#14)]  
  
### <a name="to-set-the-client-credential-type-in-configuration"></a>Установка типа учетных данных клиента в файле конфигурации  
  
1. Добавьте элемент [\<System. serviceModel >](../configure-apps/file-schema/wcf/system-servicemodel.md) в файл конфигурации.  
  
2. Добавьте в качестве дочернего элемента [\<привязки >](../configure-apps/file-schema/wcf/bindings.md) элемента.  
  
3. Добавьте соответствующую привязку. В этом примере используется элемент [\<WSHttpBinding](../configure-apps/file-schema/wcf/wshttpbinding.md) .  
  
4. Добавьте элемент [> binding\<](../configure-apps/file-schema/wcf/bindings.md) и задайте для атрибута `name` соответствующее значение. В этом примере используется имя "SecureBinding".  
  
5. Добавьте привязку `<security>`. Присвойте атрибуту `mode` соответствующее значение. В данном примере используется значение `"Message"`.  
  
6. Добавьте элемент `<message>` или `<transport>` в зависимости от режима безопасности. Присвойте атрибуту `clientCredentialType` соответствующее значение. В этом примере используется `"Windows"`.  
  
    ```xml  
    <system.serviceModel>  
      <bindings>  
        <wsHttpBinding>  
          <binding name="SecureBinding">  
            <security mode="Message">  
                 <message clientCredentialType="Windows" />  
             </security>  
          </binding>  
        </wsHttpBinding>  
      </bindings>  
    </system.serviceModel>  
    ```  
  
## <a name="see-also"></a>См. также

- [Защита служб](securing-services.md)
- [Практическое руководство. Задание режима безопасности](how-to-set-the-security-mode.md)
