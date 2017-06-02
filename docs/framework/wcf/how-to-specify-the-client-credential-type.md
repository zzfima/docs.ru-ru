---
title: "Как указывать тип учетных данных клиента | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "учетные данные безопасности, добавление в сообщения SOAP"
  - "WCF, безопасность"
ms.assetid: 10f51bee-5f92-4c1a-9126-fa5418535d8f
caps.latest.revision: 8
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 8
---
# Как указывать тип учетных данных клиента
После установки режима безопасности \(на уровне транспорта или сообщений\) можно установить тип учетных данных клиента.Это свойство определяет тип учетных данных, которые клиент должен предоставить службе для проверки подлинности.[!INCLUDE[crabout](../../../includes/crabout-md.md)] настройке режима безопасности \(обязательный шаг перед настройкой типа учетных данных клиента\) см. в разделе [Как задать режим безопасности](../../../docs/framework/wcf/how-to-set-the-security-mode.md).  
  
### Установка типа учетных данных клиента в коде  
  
1.  Создайте экземпляр привязки, который будет использовать служба.В этом примере используется привязка <xref:System.ServiceModel.WSHttpBinding>.  
  
2.  Присвойте соответствующее значение свойству <xref:System.ServiceModel.WSHttpSecurity.Mode%2A>.В этом примере используется режим Message.  
  
3.  Присвойте соответствующее значение свойству <xref:System.ServiceModel.MessageSecurityOverHttp.ClientCredentialType%2A>.В этом примере используется проверка подлинности Windows \(<xref:System.ServiceModel.MessageCredentialType>\).  
  
     [!code-csharp[c_ProgrammingSecurity#14](../../../samples/snippets/csharp/VS_Snippets_CFX/c_programmingsecurity/cs/source.cs#14)]
     [!code-vb[c_ProgrammingSecurity#14](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_programmingsecurity/vb/source.vb#14)]  
  
### Установка типа учетных данных клиента в файле конфигурации  
  
1.  Добавьте в файл конфигурации элемент [\<system.serviceModel\>](../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md).  
  
2.  Добавьте дочерний элемент [\<привязки\>](../../../docs/framework/configure-apps/file-schema/wcf/bindings.md).  
  
3.  Добавьте соответствующую привязку.В этом примере используется элемент [\<wsHttpBinding\>](../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md).  
  
4.  Добавьте элемент [\<привязка\>](../../../docs/framework/misc/binding.md) и присвойте атрибуту `name` соответствующее значение.В этом примере используется имя "SecureBinding".  
  
5.  Добавьте привязку `<security>`.Присвойте атрибуту `mode` соответствующее значение.В данном примере используется значение `"Message"`.  
  
6.  Добавьте элемент `<message>` или `<transport>` в зависимости от режима безопасности.Присвойте атрибуту `clientCredentialType` соответствующее значение.В этом примере используется `"Windows"`.  
  
    ```  
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
  
## См. также  
 [Защита служб](../../../docs/framework/wcf/securing-services.md)   
 [Как задать режим безопасности](../../../docs/framework/wcf/how-to-set-the-security-mode.md)