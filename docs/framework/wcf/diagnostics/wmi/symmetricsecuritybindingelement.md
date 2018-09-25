---
title: SymmetricSecurityBindingElement
ms.date: 03/30/2017
ms.assetid: b2e182b6-c041-4d80-a926-6058068d9f79
author: BrucePerlerMS
ms.openlocfilehash: 180b64f6f37e5c765585e52b292319816618be28
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/25/2018
ms.locfileid: "47076526"
---
# <a name="symmetricsecuritybindingelement"></a>SymmetricSecurityBindingElement
SymmetricSecurityBindingElement  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class SymmetricSecurityBindingElement : SecurityBindingElement  
{  
  string MessageProtectionOrder;  
  boolean RequireSignatureConfirmation;  
};  
```  
  
## <a name="methods"></a>Методы  
 Класс SymmetricSecurityBindingElement не определяет никаких методов.  
  
## <a name="properties"></a>Свойства  
 Класс SymmetricSecurityBindingElement имеет следующие свойства.  
  
### <a name="messageprotectionorder"></a>MessageProtectionOrder  
 Тип данных: string  
  
 Тип доступа: только для чтения  
  
 Порядок шифрования и подписывания сообщений для данной привязки.  
  
### <a name="requiresignatureconfirmation"></a>RequireSignatureConfirmation  
 Тип данных: boolean  
  
 Тип доступа: только для чтения  
  
 Указывает, требует ли привязка подтверждения подписи.  
  
## <a name="requirements"></a>Требования  
  
|MOF|Объявлено в файле Servicemodel.mof.|  
|---------|-----------------------------------|  
|Пространство имен|Определено в root\ServiceModel.|  
  
## <a name="see-also"></a>См. также  
 <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement>
