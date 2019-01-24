---
title: PrivacyNoticeBindingElement
ms.date: 03/30/2017
ms.assetid: 0cf110b1-e25b-4d67-986b-10cb04dc4826
ms.openlocfilehash: 4bdd860304c73771933d0f8500c6003ac7692aa1
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54639514"
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
  
 Тип доступа: Только чтение  
  
 Версия уведомления о конфиденциальности.  
  
### <a name="url"></a>URL-адрес  
 Тип данных: string  
  
 Тип доступа: Только чтение  
  
 URL-адрес, по которому расположено уведомление о конфиденциальности.  
  
## <a name="requirements"></a>Требования  
  
|MOF|Объявлено в файле Servicemodel.mof.|  
|---------|-----------------------------------|  
|Пространство имен|Определено в root\ServiceModel.|  
  
## <a name="see-also"></a>См. также
- <xref:System.ServiceModel.Channels.PrivacyNoticeBindingElement>
