---
title: PrivacyNoticeBindingElement
ms.date: 03/30/2017
ms.assetid: 0cf110b1-e25b-4d67-986b-10cb04dc4826
ms.openlocfilehash: a4ae5153525d5468955a09d19e534c00114c6530
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33485122"
---
# <a name="privacynoticebindingelement"></a>PrivacyNoticeBindingElement
PrivacyNoticeBindingElement  
  
## <a name="syntax"></a>Синтаксис  
  
```  
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
