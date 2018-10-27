---
title: PrivacyNoticeBindingElement
ms.date: 03/30/2017
ms.assetid: 0cf110b1-e25b-4d67-986b-10cb04dc4826
ms.openlocfilehash: fdaf30e78b1a74a733753542acd6a41f15f176bd
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/27/2018
ms.locfileid: "50194832"
---
# <a name="privacynoticebindingelement"></a>PrivacyNoticeBindingElement
PrivacyNoticeBindingElement  
  
## <a name="syntax"></a>Синтаксис  
  
```csharp
class PrivacyNoticeBindingElement : BindingElement  
{  
  sint32 PrivacyNoticeVersion;  
  string Url;  
};  
```  
  
## <a name="methods"></a>Методы  
 Класс PrivacyNoticeBindingElement не определяет никаких методов.  
  
## <a name="properties"></a>Свойства  
 Класс PrivacyNoticeBindingElement имеет следующие свойства.  
  
### <a name="privacynoticeversion"></a>PrivacyNoticeVersion  
 Тип данных: sint32  
  
 Тип доступа: только для чтения  
  
 Версия уведомления о конфиденциальности.  
  
### <a name="url"></a>URL-адрес  
 Тип данных: string  
  
 Тип доступа: только для чтения  
  
 URL-адрес, по которому расположено уведомление о конфиденциальности.  
  
## <a name="requirements"></a>Требования  
  
|MOF|Объявлено в файле Servicemodel.mof.|  
|---------|-----------------------------------|  
|Пространство имен|Определено в root\ServiceModel.|  
  
## <a name="see-also"></a>См. также  
 <xref:System.ServiceModel.Channels.PrivacyNoticeBindingElement>
