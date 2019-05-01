---
title: Возможности безопасности при использовании пользовательских привязок
ms.date: 03/30/2017
ms.assetid: a2425679-484a-4e6c-9c98-7da7304f1516
ms.openlocfilehash: 25d203fa706eeb0d0ccf1eaf4367ffa5bd7b83aa
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61990929"
---
# <a name="security-capabilities-with-custom-bindings"></a>Возможности безопасности при использовании пользовательских привязок
Основные задачи обеспечения безопасности можно выполнить, используя одну из предоставляемых системой привязок. Однако при необходимости в дополнительных элементах управления можно создать пользовательскую привязку с помощью элемента <xref:System.ServiceModel.Channels.SecurityBindingElement>, следуя объяснениям в этом разделе. Дополнительные сведения о пользовательских привязках см. в разделе [пользовательских привязок](../../../../docs/framework/wcf/extending/custom-bindings.md).  
  
## <a name="in-this-section"></a>В этом разделе  
 [Режимы проверки подлинности SecurityBindingElement](../../../../docs/framework/wcf/feature-details/securitybindingelement-authentication-modes.md)  
 Содержит описание режимов проверки подлинности, которые возможны для пользовательской привязки.  
  
 [Практическое руководство. Создание пользовательской привязки с использованием элемента SecurityBindingElement](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md)  
 Содержит описание основных шагов, которые необходимо предпринять для создания пользовательской привязки к элементу безопасности.  
  
 [Практическое руководство. Создание SecurityBindingElement для заданного режима проверки подлинности](../../../../docs/framework/wcf/feature-details/how-to-create-a-securitybindingelement-for-a-specified-authentication-mode.md)  
 Описывается, как создать элемент безопасности для заданного режима проверки подлинности.  
  
 [Практическое руководство. Отключения безопасных сеансов в WSFederationHttpBinding](../../../../docs/framework/wcf/feature-details/how-to-disable-secure-sessions-on-a-wsfederationhttpbinding.md)  
 Описывается, как отключить безопасные сеансы при создании службы федерации.  
  
 [Практическое руководство. Включение обнаружения повтора сообщений](../../../../docs/framework/wcf/feature-details/how-to-enable-message-replay-detection.md)  
 Описывается, как определить, когда будет осуществлена атака воспроизведения.  
  
 [Практическое руководство. Создание вспомогательных учетных данных](../../../../docs/framework/wcf/feature-details/how-to-create-a-supporting-credential.md)  
 Описывается, как предоставить службе подтверждающие учетные данные при необходимости.  
  
 [Практическое руководство. Настройка подтверждения сигнатуры](../../../../docs/framework/wcf/feature-details/how-to-set-up-a-signature-confirmation.md)  
 Содержит описание шагов, которые необходимо предпринять для подтверждения подписей при использовании цифровых подписей сообщений.  
  
 [Практическое руководство. Установка разницы в показаниях часов Max](../../../../docs/framework/wcf/feature-details/how-to-set-a-max-clock-skew.md)  
 Описывается, как настроить максимально допустимую разницу во времени между службой и клиентом.  
  
 [Практическое руководство. Выключение шифрования цифровых сигнатур](../../../../docs/framework/wcf/feature-details/how-to-disable-encryption-of-digital-signatures.md)  
 Описывается, как отключение шифрования цифровых подписей может увеличить производительность.  
  
## <a name="reference"></a>Ссылка  
 <xref:System.ServiceModel.Channels.SecurityBindingElement>  
  
 [\<Безопасность >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md)  
  
## <a name="related-sections"></a>Связанные разделы  
 [Основные сведения об уровне защиты](../../../../docs/framework/wcf/understanding-protection-level.md)  
  
 [Защита служб и клиентов](../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
  
## <a name="see-also"></a>См. также

- [Привязки и безопасность](../../../../docs/framework/wcf/feature-details/bindings-and-security.md)
- [Общие сведения о безопасности](../../../../docs/framework/wcf/feature-details/security-overview.md)
- [Привязки, предоставляемые системой](../../../../docs/framework/wcf/system-provided-bindings.md)
