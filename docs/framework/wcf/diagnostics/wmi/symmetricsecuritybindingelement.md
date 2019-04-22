---
title: SymmetricSecurityBindingElement
ms.date: 03/30/2017
ms.assetid: b2e182b6-c041-4d80-a926-6058068d9f79
ms.openlocfilehash: f6effd533a205d0e8fd1421119e325f06b340dd1
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59770416"
---
# <a name="symmetricsecuritybindingelement"></a>SymmetricSecurityBindingElement
SymmetricSecurityBindingElement  
  
## <a name="syntax"></a>Синтаксис  
  
```csharp
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
  
 Тип доступа: Только чтение  
  
 Порядок шифрования и подписывания сообщений для данной привязки.  
  
### <a name="requiresignatureconfirmation"></a>RequireSignatureConfirmation  
 Тип данных: boolean  
  
 Тип доступа: Только чтение  
  
 Указывает, требует ли привязка подтверждения подписи.  
  
## <a name="requirements"></a>Требования  
  
|MOF|Объявлено в файле Servicemodel.mof.|  
|---------|-----------------------------------|  
|Пространство имен|Определено в root\ServiceModel.|  
  
## <a name="see-also"></a>См. также

- <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement>
