---
title: Выборочная сериализация
ms.date: 08/07/2017
dev_langs:
- CSharp
helpviewer_keywords:
- serialization, selective serialization
- binary serialization, selective serialization
ms.assetid: 39c56635-95d2-4afd-aff1-b022e7649bb3
ms.openlocfilehash: 74e21045ec70faf6ee82200a15362d51edf61433
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/08/2018
ms.locfileid: "44186007"
---
# <a name="selective-serialization"></a>Выборочная сериализация
Класс часто содержит поля, которые не должны быть сериализованы. Например, рассмотрим класс, содержащий идентификатор потока в переменной-члене. При десериализации класса поток, в котором хранился идентификатор во время сериализации класса, может уже не использоваться, поэтому сериализация такого значения не имеет смысла. Предотвратить сериализацию переменных-членов можно, маркировав их атрибутом [NonSerialized](xref:System.NonSerializedAttribute) следующим образом.  
  
```csharp  
[Serializable]  
public class MyObject   
{  
  public int n1;  
  [NonSerialized] public int n2;  
  public String str;  
}  
```

Для объекта, содержащего важные для обеспечения безопасности данные, следует, если это возможно, запретить сериализацию. Если же для данного объекта сериализация необходима, примените к соответствующим полям с важной информацией атрибут `NonSerialized`. Учтите, что если не исключить эти поля из сериализации, хранимые в них данные предоставляются любому коду с разрешением сериализации. Дополнительные сведения о написании безопасного кода сериализации см. в разделе [Безопасность и сериализация](../../../docs/framework/misc/security-and-serialization.md).

[!INCLUDE [binary-serialization-warning](../../../includes/binary-serialization-warning.md)]
  
## <a name="see-also"></a>См. также

- [Двоичная сериализация](binary-serialization.md)  
- [Сериализация XML и SOAP](xml-and-soap-serialization.md)  
- [Безопасность и сериализация](../../../docs/framework/misc/security-and-serialization.md)
