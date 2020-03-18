---
title: AttributeUsage (C#)
ms.date: 04/25/2018
ms.openlocfilehash: a3a82e33d7259ec56ec3e907bc3d4d9f8a01167d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "61668722"
---
# <a name="attributeusage-c"></a>AttributeUsage (C#)

Определяет, как можно использовать пользовательский класс атрибутов. <xref:System.AttributeUsageAttribute> — это атрибут, примененный к определениям настраиваемого атрибута. С помощью атрибута `AttributeUsage` можно контролировать:

- Какой атрибут элементов программы можно применить. Если вы не ограничите использование, атрибут можно применить к любому из следующих элементов программы:
  - сборка
  - module
  - поле
  - событие
  - method
  - param
  - Свойство
  - return
  - type
- Можно ли применить атрибут к одному элементу программы несколько раз.
- Могут ли атрибуты наследоваться производными классами.

При явном применении параметры по умолчанию выглядят следующим образом:

[!code-csharp[Define a new attribute](../../../../../samples/snippets/csharp/attributes/NewAttribute.cs#1)]

В этом примере класс `NewAttribute` можно применить к любому поддерживаемому элементу программы. Но он применяется к каждому объекту только один раз. Атрибут наследуется производными классами при применении к базовому классу.

Аргументы <xref:System.AttributeUsageAttribute.AllowMultiple> и <xref:System.AttributeUsageAttribute.Inherited> являются необязательными, так что следующий код имеет тот же результат:

[!code-csharp[Omit optional attributes](../../../../../samples/snippets/csharp/attributes/NewAttribute.cs#2)]

Первый аргумент <xref:System.AttributeUsageAttribute> должен состоять из одного или нескольких элементов перечисления <xref:System.AttributeTargets>. Несколько типов целевого объекта можно связать с помощью оператора OR, как показано в следующем примере:

[!code-csharp[Create an attribute for fields or properties](../../../../../samples/snippets/csharp/attributes/NewPropertyOrFieldAttribute.cs#1)]

Начиная с C# 7.3 атрибуты могут применяться либо к свойству, либо к резервному полю для автоматически реализуемого свойства. Атрибут применяется к свойству, если не указан описатель `field` для атрибута. Оба случая показаны в следующем примере:

[!code-csharp[Create an attribute for fields or properties](../../../../../samples/snippets/csharp/attributes/NewPropertyOrFieldAttribute.cs#2)]

Если аргументу <xref:System.AttributeUsageAttribute.AllowMultiple> присвоено значение `true`, то результирующий атрибут можно применить несколько раз к одной сущности, как показано в следующем примере:

[!code-csharp[Create and use an attribute that can be applied multiple times](../../../../../samples/snippets/csharp/attributes/MultiUseAttribute.cs#1)]

В этом случае `MultiUseAttribute` можно применять несколько раз, так как `AllowMultiple` имеет значение `true`. Для применения нескольких атрибутов допускаются оба показанных формата.

Если <xref:System.AttributeUsageAttribute.Inherited> — `false`, атрибут не наследуется классами, производными от класса атрибутов. Пример:

[!code-csharp[Create and use an attribute that can be applied multiple times](../../../../../samples/snippets/csharp/attributes/NonInheritedAttribute.cs#1)]

В этом случае `NonInheritedAttribute` не применяется к `DClass` путем наследования.

## <a name="remarks"></a>Remarks

Атрибут `AttributeUsage` можно использовать только один раз — его нельзя повторно применять к одному и тому же классу. `AttributeUsage` является псевдонимом для <xref:System.AttributeUsageAttribute>.

Дополнительные сведения см. в разделе [Обращение к атрибутам с помощью отражения (C#)](accessing-attributes-by-using-reflection.md).

## <a name="example"></a>Пример

В приведенном ниже примере демонстрируется действие аргументов <xref:System.AttributeUsageAttribute.Inherited> и <xref:System.AttributeUsageAttribute.AllowMultiple> по отношению к атрибуту <xref:System.AttributeUsageAttribute>, а также способ перечисления настраиваемых атрибутов, примененных к классу.

[!code-csharp[Applying and querying attributes](../../../../../samples/snippets/csharp/attributes/Program.cs#1)]

## <a name="sample-output"></a>Пример выходных данных

```text
Attributes on Base Class:
FirstAttribute
SecondAttribute
Attributes on Derived Class:
ThirdAttribute
ThirdAttribute
SecondAttribute
```

## <a name="see-also"></a>См. также раздел

- <xref:System.Attribute>
- <xref:System.Reflection>
- [Руководство по программированию на C#](../..//index.md)
- [Атрибуты](../../../..//standard/attributes/index.md)
- [Отражение (C#)](../reflection.md)
- [Атрибуты](index.md)
- [Создание настраиваемых атрибутов (C#)](creating-custom-attributes.md)
- [Обращение к атрибутам с помощью отражения (C#)](accessing-attributes-by-using-reflection.md)
