---
title: Создание настраиваемых атрибутов (C#)
ms.date: 07/20/2015
ms.assetid: 500e1977-c6de-462d-abce-78a0eb1eda22
ms.openlocfilehash: c0f25adf0d562b659edaa8f36e72332fd0c1ee7e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "69595404"
---
# <a name="creating-custom-attributes-c"></a>Создание настраиваемых атрибутов (C#)
Собственные настраиваемые атрибуты можно создать, определив класс атрибута, то есть класс, прямо или косвенно наследующий от <xref:System.Attribute>, который упрощает задание определений атрибутов в метаданных. Предположим, что требуется пометить тип тегом с именем программиста, который его разработал. Вы можете определить класс настраиваемых атрибутов `Author`:  
  
```csharp  
[System.AttributeUsage(System.AttributeTargets.Class |  
                       System.AttributeTargets.Struct)  
]  
public class Author : System.Attribute  
{  
    private string name;  
    public double version;  
  
    public Author(string name)  
    {  
        this.name = name;  
        version = 1.0;  
    }  
}  
```  
  
 Имя класса — это имя атрибута, `Author`. Он является производным от `System.Attribute`, поэтому это класс настраиваемых атрибутов. Параметры конструктора являются позиционными параметрами настраиваемого атрибута. В этом примере `name` является позиционным параметром. Все открытые поля или свойства, доступные для чтения и записи, являются именованными параметрами. В этом случае `version` — единственный именованный параметр. Обратите внимание на использование атрибута `AttributeUsage`, делающего атрибут `Author` допустимым только для класса и объявлений `struct`.  
  
 Этот атрибут можно использовать следующим образом:  
  
```csharp  
[Author("P. Ackerman", version = 1.1)]  
class SampleClass  
{  
    // P. Ackerman's code goes here...  
}  
```  
  
 `AttributeUsage` имеет именованный параметр, `AllowMultiple`, с помощью которого можно задавать для настраиваемого атрибута однократное или многократное использование. В следующем примере кода создается многократно используемый атрибут.  
  
```csharp  
[System.AttributeUsage(System.AttributeTargets.Class |  
                       System.AttributeTargets.Struct,  
                       AllowMultiple = true)  // multiuse attribute  
]  
public class Author : System.Attribute  
```  
  
 В следующем примере кода несколько атрибутов одного типа применяются к классу.  
  
```csharp  
[Author("P. Ackerman", version = 1.1)]  
[Author("R. Koch", version = 1.2)]  
class SampleClass  
{  
    // P. Ackerman's code goes here...  
    // R. Koch's code goes here...  
}  
```  
  
## <a name="see-also"></a>См. также раздел

- <xref:System.Reflection>
- [Руководство по программированию на C#](../../index.md)
- [Написание настраиваемых атрибутов](../../../../standard/attributes/writing-custom-attributes.md)
- [Отражение (C#)](../reflection.md)
- [Атрибуты (C#)](./index.md)
- [Обращение к атрибутам с помощью отражения (C#)](./accessing-attributes-by-using-reflection.md)
- [AttributeUsage (C#)](./attributeusage.md)
