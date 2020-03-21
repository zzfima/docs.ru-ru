---
title: Практическое руководство. Включение обнаружения повтора сообщений
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF security
- replay detection [WCF]
- WCF, custom bindings
- WCF, security
ms.assetid: 8b847e91-69a3-49e1-9e5f-0c455e50d804
ms.openlocfilehash: 05bcddabf625e478616cce39f08b0ff8af282716
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79184953"
---
# <a name="how-to-enable-message-replay-detection"></a>Практическое руководство. Включение обнаружения повтора сообщений
Атака воспроизведения заключается в том, что злоумышленник копирует поток сообщений между двумя сторонами и воспроизводит его для одной или нескольких сторон. Если не приняты ответные меры, атакованные компьютеры обрабатывают этот поток как надлежащие сообщения, что приводит к ряду негативных последствий, таких как повторные заказы одного элемента.  
  
 Для получения дополнительной информации об [Message Replay Detection](https://docs.microsoft.com/previous-versions/msp-n-p/ff649371(v=pandp.10))обнаружении воспроизведения сообщений см.  
  
 Следующая процедура демонстрирует различные свойства, которые можно использовать для управления обнаружением воспроизведения с помощью Windows Communication Foundation (WCF).  
  
### <a name="to-control-replay-detection-on-the-client-using-code"></a>Управление обнаружением воспроизведения на стороне клиента с помощью кода  
  
1. Создайте элемент <xref:System.ServiceModel.Channels.SecurityBindingElement> для использования в привязке <xref:System.ServiceModel.Channels.CustomBinding>. Для получения дополнительной информации [см. Как: Создать пользовательские связывания с использованием SecurityBindingElement](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md). В следующем примере используется объект <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement>, созданный с помощью объекта <xref:System.ServiceModel.Channels.SecurityBindingElement.CreateKerberosBindingElement%2A> класса <xref:System.ServiceModel.Channels.SecurityBindingElement>.  
  
2. С помощью свойства <xref:System.ServiceModel.Channels.SecurityBindingElement.LocalClientSettings%2A> получите ссылку на класс <xref:System.ServiceModel.Channels.LocalClientSecuritySettings> и задайте некоторые из следующих свойств согласно необходимости:  
  
    1. `DetectReplay`. Значение типа Boolean. Управляет тем, пытается ли клиент обнаружить воспроизведение сообщений сервера. Значение по умолчанию — `true`.  
  
    2. `MaxClockSkew`. Значение <xref:System.TimeSpan>. Задает максимальную разницу по времени, допускаемую механизмом обнаружения воспроизведения между клиентом и сервером. Механизм безопасности проверяет отправленную отметку времени и определяет, не слишком ли давно она отправлена. Значение по умолчанию равно 5 минутам.  
  
    3. `ReplayWindow`. Значение `TimeSpan`. Задает максимальное время жизни сообщения в сети с момента его отправки сервером (через промежуточные узлы), прежде чем оно доставляется клиенту. Клиент отслеживает подписи сообщений, отправленных в течение последнего промежутка времени `ReplayWindow`, с целью обнаружения воспроизведения.  
  
    4. `ReplayCacheSize`. Целочисленное значение. Клиент сохраняет подписи сообщений в кэше. Этот параметр задает максимальное количество подписей, которое может храниться в кэше. Если количество сообщений, отправленных в пределах последнего окна воспроизведения, достигает предела кэша, новые сообщения отклоняются, пока не будет достигнут предел по времени для самых старых подписей в кэше. По умолчанию 500000.  
  
### <a name="to-control-replay-detection-on-the-service-using-code"></a>Управление обнаружением воспроизведения на стороне службы с помощью кода  
  
1. Создайте элемент <xref:System.ServiceModel.Channels.SecurityBindingElement> для использования в привязке <xref:System.ServiceModel.Channels.CustomBinding>.  
  
2. С помощью свойства <xref:System.ServiceModel.Channels.SecurityBindingElement.LocalServiceSettings%2A> получите ссылку на класс <xref:System.ServiceModel.Channels.LocalServiceSecuritySettings> и задайте свойства, как указано выше.  
  
### <a name="to-control-replay-detection-in-configuration-for-the-client-or-service"></a>Управление обнаружением воспроизведения с помощью конфигурации для клиента или службы  
  
1. Создайте [ \<пользовательскийобязательный>](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md).  
  
2. Создайте элемент `<security>`.  
  
3. Создайте [ \<>локальныхклиент>-клиентов](../../../../docs/framework/configure-apps/file-schema/wcf/localclientsettings-element.md) или [ \<localServiceSettings. ](../../../../docs/framework/configure-apps/file-schema/wcf/localservicesettings-element.md)  
  
4. Задайте следующие значение атрибутов (согласно необходимости): `detectReplays`, `maxClockSkew`, `replayWindow` и `replayCacheSize`. В следующем примере задаются атрибуты для обоих элементов: `<localServiceSettings>`.  
  
    ```xml  
    <customBinding>  
      <binding name="NewBinding0">  
       <textMessageEncoding />  
        <security>  
         <localClientSettings
          replayCacheSize="800000"
          maxClockSkew="00:03:00"  
          replayWindow="00:03:00" />  
         <localServiceSettings
          replayCacheSize="800000"
          maxClockSkew="00:03:00"  
          replayWindow="00:03:00" />  
        <secureConversationBootstrap />  
       </security>  
      <httpTransport />  
     </binding>  
    </customBinding>  
    ```  
  
## <a name="example"></a>Пример  
 В следующем примере создается элемент <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement> с помощью метода <xref:System.ServiceModel.Channels.SecurityBindingElement.CreateKerberosBindingElement%2A> и задает свойства воспроизведения привязки.  
  
 [!code-csharp[c_ReplayDetection#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_replaydetection/cs/source.cs#1)]
 [!code-vb[c_ReplayDetection#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_replaydetection/vb/source.vb#1)]  
  
## <a name="scope-of-replay-message-security-only"></a>Область воспроизведения: только для режима безопасности сообщений  
 Обратите внимание, что следующие процедуры применяются только для режима безопасности сообщений. В режиме транспорта и в режиме транспорта с учетными данными сообщения воспроизведение обнаруживает транспортный механизм.  
  
## <a name="secure-conversation-notes"></a>Примечания о безопасном диалоге  
 Для привязок, обеспечивающих безопасные диалоги, можно изменить эти настройки и для канала приложения, и для привязки начальной загрузки безопасного диалога. Например, можно отключить воспроизведение для канала приложения, но разрешить его для канала начальной загрузки, устанавливающего безопасный диалог.  
  
 Если сеансы безопасных диалогов не используются, средства обнаружения воспроизведения не гарантируют обнаружение воспроизведения в случаях использования фермы серверов и перезапуска процесса. Это относится к следующим привязкам, предоставляемым системой:  
  
- <xref:System.ServiceModel.BasicHttpBinding>.  
  
- Привязка <xref:System.ServiceModel.WSHttpBinding>, в которой свойство <xref:System.ServiceModel.NonDualMessageSecurityOverHttp.EstablishSecurityContext%2A> имеет значение `false`.  
  
## <a name="compiling-the-code"></a>Компиляция кода  
  
- Для компиляции кода требуются следующие пространства имен.  
  
- <xref:System>  
  
- <xref:System.ServiceModel>  
  
- <xref:System.ServiceModel.Channels>  
  
## <a name="see-also"></a>См. также раздел

- <xref:System.ServiceModel.Channels.LocalClientSecuritySettings>
- <xref:System.ServiceModel.Channels.LocalServiceSecuritySettings>
- [Безопасные диалоги и безопасные сеансы](../../../../docs/framework/wcf/feature-details/secure-conversations-and-secure-sessions.md)
- [\<местныеклиентыНастройки>](../../../../docs/framework/configure-apps/file-schema/wcf/localclientsettings-element.md)
- [Практическое руководство. Создание пользовательской привязки с использованием элемента SecurityBindingElement](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md)
