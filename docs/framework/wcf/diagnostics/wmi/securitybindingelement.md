---
title: SecurityBindingElement
ms.date: 03/30/2017
ms.assetid: ef93b6e6-3524-48a8-94d3-c8837f1872f9
ms.openlocfilehash: 1d367d0c5d14e6e75539dd2b20cdffcf2b34963d
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59153859"
---
# <a name="securitybindingelement"></a>SecurityBindingElement
SecurityBindingElement  
  
## <a name="syntax"></a>Синтаксис  
  
```csharp
class SecurityBindingElement : BindingElement  
{  
  string DefaultAlgorithmSuite;  
  boolean IncludeTimestamp;  
  string KeyEntropyMode;  
  LocalServiceSecuritySettings LocalServiceSecuritySettings;  
  string MessageSecurityVersion;  
  string SecurityHeaderLayout;  
};  
```  
  
## <a name="methods"></a>Методы  
 Класс SecurityBindingElement не определяет никаких методов.  
  
## <a name="properties"></a>Свойства  
 Класс SecurityBindingElement имеет следующие свойства.  
  
### <a name="defaultalgorithmsuite"></a>DefaultAlgorithmSuite  
 Тип данных: string  
  
 Тип доступа: Только чтение  
  
 Задает алгоритмы, используемые в сочетании с привязкой.  
  
### <a name="includetimestamp"></a>IncludeTimestamp  
 Тип данных: boolean  
  
 Тип доступа: Только чтение  
  
 Логическое значение, указывающее, будет ли в каждое сообщение вноситься метка времени.  
  
### <a name="keyentropymode"></a>KeyEntropyMode  
 Тип данных: string  
  
 Тип доступа: Только чтение  
  
 Источник энтропии, используемый для создания ключей.  
  
### <a name="localservicesecuritysettings"></a>LocalServiceSecuritySettings  
 Тип данных: LocalServiceSecuritySettings  
  
 Тип доступа: Только чтение  
  
 Свойства безопасности для локальной службы, соответствующие данной привязке.  
  
### <a name="messagesecurityversion"></a>MessageSecurityVersion  
 Тип данных: string  
  
 Тип доступа: Только чтение  
  
 Версия, используемая для безопасности сообщения.  
  
### <a name="securityheaderlayout"></a>SecurityHeaderLayout  
 Тип данных: string  
  
 Тип доступа: Только чтение  
  
 Порядок элементов в заголовке безопасности для данной привязки.  
  
## <a name="requirements"></a>Требования  
  
|MOF|Объявлено в файле Servicemodel.mof.|  
|---------|-----------------------------------|  
|Пространство имен|Определено в root\ServiceModel.|  
  
## <a name="see-also"></a>См. также

- <xref:System.ServiceModel.Channels.SecurityBindingElement>
