---
title: CustomBindingElement
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: df959dc5-1aef-4338-a123-6ff3e7bc37af
caps.latest.revision: "9"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 6edf2e06b758f9f70d418977a68b2403cecc1f51
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="custombindingelement"></a>CustomBindingElement
CustomBindingElement  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CustomBindingElement : BindingElement  
{  
  string Name;  
};  
```  
  
## <a name="methods"></a>Методы  
 Класс CustomBindingElement не определяет никаких методов.  
  
## <a name="properties"></a>Свойства  
 Класс CustomBindingElement имеет следующее свойство:  
  
### <a name="name"></a>Имя  
 Тип данных: string  
  
 Тип доступа: только для чтения  
  
 Строка, содержащая имя конфигурации привязки. Это значение является определяемой пользователем строкой, которая используется как строка идентификации для пользовательской привязки.  
  
## <a name="requirements"></a>Требования  
  
|MOF|Объявлено в файле Servicemodel.mof.|  
|---------|-----------------------------------|  
|Пространство имен|Определено в root\ServiceModel.|  
  
## <a name="see-also"></a>См. также  
 <xref:System.ServiceModel.Channels.CustomBinding>
