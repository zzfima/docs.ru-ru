---
title: "Интеграция с приложениями COM"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Windows Communication Foundation, COM integration
- COM [WCF], Windows Communication Foundation integration
- WCF, reusing code
- Windows Communication Foundation, reusing code
- COM [WCF]
- WCF, COM integration
ms.assetid: c98bda3e-6779-419e-8e6d-9aa94053026d
caps.latest.revision: "9"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: a0e625beaf20f6445099d8fb15cb175d3d71a860
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="integrating-with-com-applications"></a>Интеграция с приложениями COM
Службы [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] можно объединить непосредственно с существующим кодом с помощью моникера службы [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]. Моникер служб можно использовать в широком наборе сред разработки на базе модели COM, например в Office VBA, Visual Basic 6.0 и Visual C++ 6.0.  
  
## <a name="in-this-section"></a>Содержание  
 [Интеграция с Общие сведения о приложениях COM](../../../../docs/framework/wcf/feature-details/integrating-with-com-applications-overview.md)  
 Предоставляет общие сведения об основных компонентах процесса объединения.  
  
 [Как: регистрация и настройка моникера службы](../../../../docs/framework/wcf/feature-details/how-to-register-and-configure-a-service-moniker.md)  
 Чтобы начать использовать моникер службы [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] в рамках приложения COM, зарегистрируйте необходимые типы с атрибутами с помощью COM и настройте приложение COM и моникер в соответствии с необходимой конфигурацией привязки.  
  
 [Как: использование моникера службы Windows Communication Foundation без регистрации](../../../../docs/framework/wcf/feature-details/use-the-wcf-service-moniker-without-registration.md)  
 Содержит объяснения, как получить определение контракта в форме документа языка описания веб-служб (WSDL) или из конечной точки WS-MetadataExchange.  
  
 [Как: использование моникера службы с контрактами WSDL](../../../../docs/framework/wcf/feature-details/how-to-use-a-service-moniker-with-wsdl-contracts.md)  
 Содержит описание, как вызвать пример [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] с помощью моникера WSDL [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].  
  
 [Как: использование моникера службы с контрактами обмена метаданными](../../../../docs/framework/wcf/feature-details/how-to-use-a-service-moniker-with-metadata-exchange-contracts.md)  
 Содержит описание, как вызывать пример [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] с помощью моникера [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], указывающего конечную точку обмена метаданными (Mex).  
  
 [Как: укажите учетные данные безопасности канала](../../../../docs/framework/wcf/feature-details/how-to-specify-channel-security-credentials.md)  
 Моникер службы [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] поддерживает интерфейс `IChannelCredentials`, который обеспечивает ряд альтернативных методов указания учетных данных каналов.  
  
## <a name="reference"></a>Ссылка  
 <xref:System.ServiceModel>  
  
## <a name="see-also"></a>См. также  
 [Интеграция с приложениями COM +](../../../../docs/framework/wcf/feature-details/integrating-with-com-plus-applications.md)
