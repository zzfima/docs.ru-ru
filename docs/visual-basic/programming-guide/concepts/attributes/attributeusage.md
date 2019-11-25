---
title: AttributeUsage
ms.date: 07/20/2015
ms.assetid: 48757216-c21d-4051-86d5-8a3e03c39d2c
ms.openlocfilehash: 7e54e82c1e9edfd0d9d393a014f9d91f82970363
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74353544"
---
# <a name="attributeusage-visual-basic"></a>AttributeUsage (Visual Basic)

Определяет, как можно использовать пользовательский класс атрибутов. Атрибут `AttributeUsage` можно применять к пользовательским определениям атрибутов, чтобы контролировать применение нового атрибута. При явном применении параметры по умолчанию выглядят следующим образом:

```vb
<System.AttributeUsage(System.AttributeTargets.All,
                   AllowMultiple:=False,
                   Inherited:=True)>
Class NewAttribute
    Inherits System.Attribute
End Class
```

В этом примере класс `NewAttribute` можно применить к любой сущности кода с атрибутами, но только один раз к каждой сущности. Он наследуется производными классами при применении к базовому классу.

Аргументы `AllowMultiple` и `Inherited` являются необязательными, так что этот код имеет тот же результат:

```vb
<System.AttributeUsage(System.AttributeTargets.All)>
Class NewAttribute
    Inherits System.Attribute
End Class
```

Первый аргумент `AttributeUsage` должен состоять из одного или нескольких элементов перечисления <xref:System.AttributeTargets>. Несколько целевых типов можно связать с помощью оператора OR следующим образом:

```vb
<AttributeUsage(AttributeTargets.Property Or AttributeTargets.Field)>
Class NewPropertyOrFieldAttribute
    Inherits Attribute
End Class
```

Если аргументу `AllowMultiple` присвоено значение `true`, то результирующий атрибут можно применить несколько раз к одной сущности следующим образом:

```vb
<AttributeUsage(AttributeTargets.Class, AllowMultiple:=True)>
Class MultiUseAttr
    Inherits Attribute
End Class

<MultiUseAttr(), MultiUseAttr()>
Class Class1
End Class
```

В этом случае `MultiUseAttr` можно применять несколько раз, так как `AllowMultiple` имеет значение `true`. Для применения нескольких атрибутов допускаются оба показанных формата.

Если `Inherited` имеет значение `false`, то атрибут не наследуется классами, производными от класса с атрибутами. Пример:

```vb
<AttributeUsage(AttributeTargets.Class, Inherited:=False)>
Class Attr1
    Inherits Attribute
End Class

<Attr1()>
Class BClass

End Class

Class DClass
    Inherits BClass
End Class
```

В этом случае `Attr1` не применяется к `DClass` путем наследования.

## <a name="remarks"></a>Заметки

Атрибут `AttributeUsage` можно использовать только один раз — его нельзя повторно применять к одному и тому же классу. `AttributeUsage` является псевдонимом для <xref:System.AttributeUsageAttribute>.

Дополнительные сведения см. в статье [Accessing Attributes by Using Reflection (Visual Basic)](../../../../visual-basic/programming-guide/concepts/attributes/accessing-attributes-by-using-reflection.md) (Обращение к атрибутам с помощью отражения (Visual Basic)).

## <a name="example"></a>Пример

В приведенном ниже примере демонстрируется действие аргументов `Inherited` и `AllowMultiple` по отношению к атрибуту `AttributeUsage`, а также способ перечисления настраиваемых атрибутов, примененных к классу.

```vb
' Create some custom attributes:
<AttributeUsage(System.AttributeTargets.Class, Inherited:=False)>
Class A1
    Inherits System.Attribute
End Class

<AttributeUsage(System.AttributeTargets.Class)>
Class A2
    Inherits System.Attribute
End Class

<AttributeUsage(System.AttributeTargets.Class, AllowMultiple:=True)>
Class A3
    Inherits System.Attribute
End Class

' Apply custom attributes to classes:
<A1(), A2()>
Class BaseClass

End Class

<A3(), A3()>
Class DerivedClass
    Inherits BaseClass
End Class

Public Class TestAttributeUsage
    Sub Main()
        Dim b As New BaseClass
        Dim d As New DerivedClass
        ' Display custom attributes for each class.
        Console.WriteLine("Attributes on Base Class:")
        Dim attrs() As Object = b.GetType().GetCustomAttributes(True)

        For Each attr In attrs
            Console.WriteLine(attr)
        Next

        Console.WriteLine("Attributes on Derived Class:")
        attrs = d.GetType().GetCustomAttributes(True)
        For Each attr In attrs
            Console.WriteLine(attr)
        Next
    End Sub
End Class
```

## <a name="sample-output"></a>Пример результатов выполнения

```console
Attributes on Base Class:
A1
A2
Attributes on Derived Class:
A3
A3
A2
```

## <a name="see-also"></a>См. также

- <xref:System.Attribute>
- <xref:System.Reflection>
- [Руководство по программированию на Visual Basic](../../../../visual-basic/programming-guide/index.md)
- [Атрибуты](../../../../standard/attributes/index.md)
- [Reflection (Visual Basic)](../../../../visual-basic/programming-guide/concepts/reflection.md) (Отражение (Visual Basic))
- [Атрибуты (Visual Basic)](../../../../visual-basic/language-reference/attributes.md)
- [Creating Custom Attributes (Visual Basic)](../../../../visual-basic/programming-guide/concepts/attributes/creating-custom-attributes.md) (Создание настраиваемых атрибутов (Visual Basic))
- [Accessing Attributes by Using Reflection (Visual Basic)](../../../../visual-basic/programming-guide/concepts/attributes/accessing-attributes-by-using-reflection.md) (Обращение к атрибутам с помощью отражения (Visual Basic))
