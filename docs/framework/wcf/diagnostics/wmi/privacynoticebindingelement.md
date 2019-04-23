---
title: PrivacyNoticeBindingElement
ms.date: 03/30/2017
ms.assetid: 0cf110b1-e25b-4d67-986b-10cb04dc4826
ms.openlocfilehash: 04c65d0aa589d99766b4ffc8f1550036d2880718
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2019
ms.locfileid: "59976382"
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
