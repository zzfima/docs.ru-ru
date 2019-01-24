---
title: Как выполнить Установка разницы в показаниях часов Max
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- MaxClockSkew property
- WCF, custom bindings
ms.assetid: 491d1705-eb29-43c2-a44c-c0cf996f74eb
ms.openlocfilehash: 73c3bd7c8bf02fd003510c838fec45a68829fe1c
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54646884"
---
# <a name="how-to-set-a-max-clock-skew"></a>Как выполнить Установка разницы в показаниях часов Max
Если настройки времени в двух компьютерах различаются, возможен сбой критичных по времени функций. Чтобы устранить такую возможность, можно задать для свойства `MaxClockSkew` значение <xref:System.TimeSpan>. Это свойство предусмотрено в двух классах.  
  
 <xref:System.ServiceModel.Channels.LocalClientSecuritySettings>  
  
 <xref:System.ServiceModel.Channels.LocalServiceSecuritySettings>  
  
> [!IMPORTANT]
>  Внимание для безопасного диалога изменения `MaxClockSkew` свойства должны производиться начальную загрузку службы или клиента. Чтобы сделать это, необходимо задать свойство на <xref:System.ServiceModel.Channels.SecurityBindingElement> возвращаемый <xref:System.ServiceModel.Security.Tokens.SecureConversationSecurityTokenParameters.BootstrapSecurityBindingElement%2A>.  
  
 Чтобы изменить это свойство в одной из привязок, предоставляемых системой, необходимо найти элемент привязки безопасности в коллекции привязок и задать для свойства `MaxClockSkew` новое значение. От класса <xref:System.ServiceModel.Channels.SecurityBindingElement> наследуют два класса: <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement> и <xref:System.ServiceModel.Channels.AsymmetricSecurityBindingElement>. При извлечении привязки безопасности из коллекции необходимо приведение к одному из этих типов, чтобы правильно задать свойство `MaxClockSkew`. В следующем примере используется привязка <xref:System.ServiceModel.WSHttpBinding>, которая использует класс <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement>. Список с указанием, какой тип привязки безопасности следует использовать в каждой привязке, предоставляемой системой, см. в разделе [System-Provided Bindings](../../../../docs/framework/wcf/system-provided-bindings.md).  
  
### <a name="to-create-a-custom-binding-with-a-new-clock-skew-value-in-code"></a>Создание пользовательской привязки с новым значением разницы в показаниях часов в коде  
  
1.  > [!WARNING]
    >  Обратите внимание, добавить ссылки на следующие пространства имен в коде: <xref:System.ServiceModel.Channels>, <xref:System.ServiceModel.Description>, <xref:System.Security.Permissions>, и <xref:System.ServiceModel.Security.Tokens>.  
  
     Создайте новый экземпляр класса <xref:System.ServiceModel.WSHttpBinding> и задайте для него режим безопасности <xref:System.ServiceModel.SecurityMode.Message>.  
  
2.  Создайте новый экземпляр класса <xref:System.ServiceModel.Channels.BindingElementCollection>, вызвав метод <xref:System.ServiceModel.WSHttpBinding.CreateBindingElements%2A>.  
  
3.  С помощью метода <xref:System.ServiceModel.Channels.BindingElementCollection.Find%2A> класса <xref:System.ServiceModel.Channels.BindingElementCollection> найдите требуемый элемент привязки безопасности.  
  
4.  При использовании метода <xref:System.ServiceModel.Channels.BindingElementCollection.Find%2A> выполните приведение к фактическому типу. В приведенном ниже примере производится приведение к типу <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement>.  
  
5.  Задайте свойство <xref:System.ServiceModel.Channels.LocalServiceSecuritySettings.MaxClockSkew%2A> в элементе привязки безопасности.  
  
6.  Создайте <xref:System.ServiceModel.ServiceHost> с требуемыми типом и базовым адресом службы.  
  
7.  С помощью метода <xref:System.ServiceModel.ServiceHost.AddServiceEndpoint%2A> добавьте конечную точку и включите <xref:System.ServiceModel.Channels.CustomBinding>.  
  
     [!code-csharp[c_MaxClockSkew#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_maxclockskew/cs/source.cs#1)]
     [!code-vb[c_MaxClockSkew#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_maxclockskew/vb/source.vb#1)]  
  
### <a name="to-set-the-maxclockskew-in-configuration"></a>Задание MaxClockSkew в конфигурации  
  
1.  Создание [ \<customBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) в [ \<привязки >](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) раздел элемента.  
  
2.  Создание [ \<привязки >](../../../../docs/framework/misc/binding.md) и присвойте `name` атрибут соответствующее значение. В следующем примере задается значение `MaxClockSkewBinding`.  
  
3.  Добавьте элемент кодирования. Приведенный ниже пример добавляет [ \<textMessageEncoding >](../../../../docs/framework/configure-apps/file-schema/wcf/textmessageencoding.md).  
  
4.  Добавить [ \<безопасности >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) и присвойте `authenticationMode` требуемое значение атрибута. В следующем примере для этого атрибута задается значение `Kerberos`, чтобы задать, что в службе используется проверка подлинности Windows.  
  
5.  Добавить [ \<localServiceSettings >](../../../../docs/framework/configure-apps/file-schema/wcf/localservicesettings-element.md) и задайте `maxClockSkew` значение в виде атрибута `"##:##:##"`. В следующем примере задается значение 7 минут. При необходимости добавьте [ \<localServiceSettings >](../../../../docs/framework/configure-apps/file-schema/wcf/localservicesettings-element.md) и задайте `maxClockSkew` требуемое значение атрибута.  
  
6.  Добавьте транспортный элемент. В следующем примере используется [ \<httpTransport >](../../../../docs/framework/configure-apps/file-schema/wcf/httptransport.md).  
  
7.  Для безопасного диалога параметры безопасности должны задаваться при начальной загрузке в [ \<secureConversationBootstrap >](../../../../docs/framework/configure-apps/file-schema/wcf/secureconversationbootstrap.md) элемент.  
  
    ```xml  
    <bindings>  
      <customBinding>  
        <binding name="MaxClockSkewBinding">  
            <textMessageEncoding />  
            <security authenticationMode="Kerberos">  
               <localClientSettings maxClockSkew="00:07:00" />  
               <localServiceSettings maxClockSkew="00:07:00" />  
               <secureConversationBootstrap>  
                  <localClientSettings maxClockSkew="00:30:00" />  
                  <localServiceSettings maxClockSkew="00:30:00" />  
               </secureConversationBootstrap>  
            </security>  
            <httpTransport />  
        </binding>  
      </customBinding>  
    </bindings>  
    ```  
  
## <a name="see-also"></a>См. также
- <xref:System.ServiceModel.Channels.LocalClientSecuritySettings>
- <xref:System.ServiceModel.Channels.LocalServiceSecuritySettings>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [Практическое руководство. Создание пользовательской привязки с использованием элемента SecurityBindingElement](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md)
