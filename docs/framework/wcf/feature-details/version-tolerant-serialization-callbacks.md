---
title: "Обратные вызовы сериализации, независимые от версий"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- OnDeserializedAttribute [WCF]
- OnDeserializingAttribute [WCF]
- OnSerializingAttribute [WCF]
- serialization [WCF], setting default values
- OnSerializedAttribute [WCF]
ms.assetid: aa4a3a6f-05ec-4efd-bdbf-2181e13e6468
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: b6e8606b8dbc0733632c2a6dc6aeb039f5277990
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="version-tolerant-serialization-callbacks"></a>Обратные вызовы сериализации, независимые от версий
Модель программирования контракта данных полностью поддерживает методы обратных вызовов независимой от версий сериализации, которые в свою очередь поддерживают классы <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> и <xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter>.  
  
## <a name="version-tolerant-attributes"></a>Атрибуты независимой от версий сериализации  
 Существует четыре атрибута обратных вызовов. Каждый атрибут можно применить к методу, который вызывает ядро сериализации/десериализации в те или иные моменты времени. В таблице ниже представлены правила использования каждого атрибута.  
  
|Атрибут|Когда вызывается соответствующий метод|  
|---------------|---------------------------------------------|  
|<xref:System.Runtime.Serialization.OnSerializingAttribute>|Вызывается перед сериализацией типа.|  
|<xref:System.Runtime.Serialization.OnSerializedAttribute>|Вызывается после сериализации типа.|  
|<xref:System.Runtime.Serialization.OnDeserializingAttribute>|Вызывается перед десериализацией типа.|  
|<xref:System.Runtime.Serialization.OnDeserializedAttribute>|Вызывается после десериализации типа.|  
  
 Методы должны принимать параметр <xref:System.Runtime.Serialization.StreamingContext>.  
  
 Эти методы в первую очередь предназначены для использования с управлением версиями или инициализацией. Во время десериализации конструкторы не вызываются. Поэтому возможна некорректная инициализация элементов данных (согласно заданным значениям по умолчанию), если данные для этих элементов отсутствуют во входящем потоке, например, если данные поступают из предыдущей версии типа, в котором отсутствуют некоторые элементы данных. Чтобы исправить такую ситуацию, используйте метод обратных вызовов, отмеченный <xref:System.Runtime.Serialization.OnDeserializingAttribute>, как показано в следующем примере.  
  
 Для каждого типа можно отметить только один метод каждым из предыдущих атрибутов обратных вызовов.  
  
### <a name="example"></a>Пример  
 [!code-csharp[C_DataContract#9](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_datacontract/cs/source.cs#9)]
 [!code-vb[C_DataContract#9](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_datacontract/vb/source.vb#9)]  
  
## <a name="see-also"></a>См. также  
 <xref:System.Runtime.Serialization.OnSerializingAttribute>  
 <xref:System.Runtime.Serialization.OnSerializedAttribute>  
 <xref:System.Runtime.Serialization.OnDeserializingAttribute>  
 <xref:System.Runtime.Serialization.OnDeserializedAttribute>  
 <xref:System.Runtime.Serialization.StreamingContext>  
 [Независимая от версий сериализация](../../../../docs/standard/serialization/version-tolerant-serialization.md)
