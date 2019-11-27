---
title: Общие сведения об атрибутах
ms.date: 07/20/2015
ms.assetid: 1449f69b-c063-41de-8d89-f0bbdcf96ac6
ms.openlocfilehash: 97a2a13102718b6ee8829fca678b2b49df21e5d1
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74349484"
---
# <a name="attributes-overview-visual-basic"></a>Общие сведения об атрибутах (Visual Basic)

Атрибуты предоставляют мощное средство для связывания метаданных или декларативной информации с кодом (сборки, типы, методы, свойства и т. д.). Связав атрибут связан с сущностью программы, вы можете проверять этот атрибут во время выполнения, используя технику *отражения*. Дополнительные сведения см. в статье [Отражение (Visual Basic)](../../../../visual-basic/programming-guide/concepts/reflection.md).

Атрибуты имеют следующие свойства.

- Атрибуты добавляют в программу метаданные. *Метаданные* — это сведения о типах, определенных в программе. Все сборки .NET содержат некоторый набор метаданных, описывающих типы и члены типов, определенные в этой сборке. Вы можете добавить пользовательские атрибуты, чтобы указать любую дополнительную информацию. Дополнительные сведения см. в статье [Creating Custom Attributes (Visual Basic)](../../../../visual-basic/programming-guide/concepts/attributes/creating-custom-attributes.md) (Создание пользовательских атрибутов (Visual Basic)).

- Вы можете применить один или несколько атрибутов ко всей сборке, к модулю или к более мелким элементам программы, например к классам и свойствам.

- Атрибуты могут принимать аргументы, так же как методы и свойства.

- Программа может проверить собственные метаданные или метаданные в других программах, используя отражение. Дополнительные сведения см. в статье [Accessing Attributes by Using Reflection (Visual Basic)](../../../../visual-basic/programming-guide/concepts/attributes/accessing-attributes-by-using-reflection.md) (Обращение к атрибутам с помощью отражения (Visual Basic)).

## <a name="using-attributes"></a>Использование атрибутов

Атрибуты можно использовать почти в любых объявлениях, но для каждого атрибута можно ограничить типы объявлений, в которых он является допустимым. В Visual Basic атрибуты заключаются в угловые скобки (\< >). Они должны располагаться непосредственно перед тем элементом, к которому они применяются, и обязательно в той же строке.

В этом примере атрибут <xref:System.SerializableAttribute> используется для применения определенной характеристики к классу:

```vb
<System.Serializable()> Public Class SampleClass
    ' Objects of this type can be serialized.
End Class
```

 Метод с атрибутом <xref:System.Runtime.InteropServices.DllImportAttribute> объявляется следующим образом:

```vb
Imports System.Runtime.InteropServices
```

```vb
<System.Runtime.InteropServices.DllImport("user32.dll")>
Sub SampleMethod()
End Sub
```

В объявлении можно разместить несколько атрибутов:

```vb
Imports System.Runtime.InteropServices
```

```vb
Sub MethodA(<[In](), Out()> ByVal x As Double)
End Sub
Sub MethodB(<Out(), [In]()> ByVal x As Double)
End Sub
```

Некоторые атрибуты можно указать для одной сущности более одного раза. Пример такого многократно используемого атрибута — <xref:System.Diagnostics.ConditionalAttribute>:

```vb
<Conditional("DEBUG"), Conditional("TEST1")>
Sub TraceMethod()
End Sub
```

> [!NOTE]
> По соглашению все имена атрибутов заканчиваются словом "Attribute", чтобы отличать их от других элементов платформы .NET Framework. Но при использовании атрибута в коде этот суффикс можно не указывать. Например, обращение `[DllImport]` эквивалентно `[DllImportAttribute]`, хотя в .NET Framework этот атрибут имеет имя `DllImportAttribute`.

### <a name="attribute-parameters"></a>Параметры атрибутов

Многие атрибуты имеют параметры, которые могут быть позиционными, неименованными или именованными. Позиционные параметры необходимо указывать в строгом порядке и их нельзя опускать. Именованные параметры являются необязательными и их можно указывать в любом порядке. Сначала указываются позиционные параметры. Например, эти три атрибута являются эквивалентными:

```vb
<DllImport("user32.dll")>
<DllImport("user32.dll", SetLastError:=False, ExactSpelling:=False)>
<DllImport("user32.dll", ExactSpelling:=False, SetLastError:=False)>
```

Первый параметр (имя библиотеки DLL) является позиционным и всегда располагается первым, остальные параметры являются именованными. В этом примере оба именованных параметра имеют значение по умолчанию (false), и мы можем их опустить. Сведения о значениях параметров по умолчанию указываются в документации по каждому отдельному атрибуту.

### <a name="attribute-targets"></a>Целевые объекты атрибутов

*Целевой объект* атрибута — это сущность, к которой применяется атрибут. Например, атрибут можно применить к классу, отдельному методу или ко всей сборке. По умолчанию атрибут применяется к тому элементу, перед которым он указан. Но у вас есть возможность явным образом указать, например, что атрибут применяется к методу, параметру или возвращаемому значению.

Чтобы явным образом определить целевой объект атрибута, используйте следующий синтаксис:

```vb
<target : attribute-list>
```

Возможные значения `target` перечислены в следующей таблице.

|Целевое значение|Применение|
|------------------|----------------|
|`assembly`|Вся сборка|
|`module`|Текущий модуль сборки (это не то же самое, что модуль Visual Basic)|

 Следующий пример демонстрирует, как применить атрибуты к сборкам и модулям. Дополнительные сведения см. в статье [Common Attributes (Visual Basic)](../../../../visual-basic/programming-guide/concepts/attributes/common-attributes.md) (Распространенные атрибуты (Visual Basic)).

```vb
Imports System.Reflection
<Assembly: AssemblyTitleAttribute("Production assembly 4"),
Module: CLSCompliant(True)>
```

## <a name="common-uses-for-attributes"></a>Популярные методы применения атрибутов

В следующем списке перечислены несколько распространенных применений для атрибутов.

- Указание для методов в веб-службах атрибута `WebMethod`, который обозначает, что метод должен вызываться по протоколу SOAP. Дополнительные сведения см. в разделе <xref:System.Web.Services.WebMethodAttribute>.

- Описание способов упаковки параметров методов при взаимодействии с машинным кодом. Дополнительные сведения см. в разделе <xref:System.Runtime.InteropServices.MarshalAsAttribute>.

- Описание свойств COM для классов, методов и интерфейсов.

- Вызов неуправляемого кода с помощью класса <xref:System.Runtime.InteropServices.DllImportAttribute>.

- Указание для сборки таких параметров, как заголовок, версия, описание или товарный знак.

- Указание членов класса, которые будут сериализованы при сохранении класса.

- Описание правил сопоставления членов класса с XML-узлами при XML-сериализации.

- Описание требований безопасности для методов.

- Указание характеристик, используемых для обеспечения безопасности.

- Управление оптимизацией для JIT-компилятора, сохраняя при этом простоту отладки кода.

- Получение сведений об объекте, вызывающем метод.

## <a name="related-sections"></a>Связанные разделы

Дополнительные сведения см. на странице

- [Creating Custom Attributes (Visual Basic)](../../../../visual-basic/programming-guide/concepts/attributes/creating-custom-attributes.md) (Создание настраиваемых атрибутов (Visual Basic))

- [Accessing Attributes by Using Reflection (Visual Basic)](../../../../visual-basic/programming-guide/concepts/attributes/accessing-attributes-by-using-reflection.md) (Обращение к атрибутам с помощью отражения (Visual Basic))

- [How to: Create a C/C++ Union by Using Attributes (Visual Basic)](../../../../visual-basic/programming-guide/concepts/attributes/how-to-create-a-c-cpp-union-by-using-attributes.md) (Практическое руководство. Создание объединения C/C++ с помощью атрибутов (Visual Basic))

- [Common Attributes (Visual Basic)](../../../../visual-basic/programming-guide/concepts/attributes/common-attributes.md) (Распространенные атрибуты (Visual Basic))

- [Caller Information (Visual Basic)](../../../../visual-basic/programming-guide/concepts/caller-information.md) (Сведения о вызывающем (Visual Basic))

## <a name="see-also"></a>См. также

- [Руководство по программированию на Visual Basic](../../../../visual-basic/programming-guide/index.md)
- [Reflection (Visual Basic)](../../../../visual-basic/programming-guide/concepts/reflection.md) (Отражение (Visual Basic))
- [Атрибуты](../../../../standard/attributes/index.md)
