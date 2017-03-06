---
title: "Смена регистра"
description: "Смена регистра"
keywords: .NET, .NET Core
author: stevehoag
ms.author: shoag
ms.date: 07/26/2016
ms.topic: article
ms.prod: .net
ms.technology: dotnet-standard
ms.devlang: dotnet
ms.assetid: 646c5afd-8aec-4393-9c00-f68ad2580c68
translationtype: Human Translation
ms.sourcegitcommit: 90fe68f7f3c4b46502b5d3770b1a2d57c6af748a
ms.openlocfilehash: 023f40969095627242d3652add853eb999c30c4b
ms.lasthandoff: 03/02/2017

---

# <a name="changing-case"></a>Смена регистра

При написании приложения, которое принимает входные данные от пользователя, невозможно предугадать, какой регистр будет использоваться для ввода данных. Часто требуется обеспечить согласованность регистра строк, особенно если они отображаются в пользовательском интерфейсе. В таблице ниже описаны два метода изменения регистра.

Имя метода | Применение
----------- | ---
[String.ToUpper](xref:System.String.ToUpper) | Преобразует все символы в строке в верхний регистр.
[String.ToLower](xref:System.String.ToLower) | Преобразует все символы в строке в нижний регистр.

> [!WARNING]  
> Обратите внимание, что методы `String.ToUpper` и `String.ToLower` не следует использовать для преобразования строк с целью их сравнения или проверки на равенство. 

## <a name="comparing-strings-of-mixed-case"></a>Сравнение строк, содержащих символы в разных регистрах

Чтобы сравнить строки, содержащие символы в разных регистрах для их упорядочения, вызовите одну из перегрузок метода [String](xref:System) `Equals` с параметром *comparisonType* и укажите значение [StringComparison.CurrentCultureIgnoreCase](xref:System.StringComparison.CurrentCultureIgnoreCase) или [StringComparison.OrdinalIgnoreCase](xref:System.StringComparison.OrdinalIgnoreCase) для аргумента *comparisonType*. 

Дополнительные сведения см. в разделе [Рекомендации по использованию строк](best-practices.md). 

## <a name="toupper"></a>ToUpper

Метод [String.ToUpper](xref:System.String.ToUpper) преобразует все символы в строке в верхний регистр. В примере ниже смешанный регистр строки "Hello World!" изменяется на верхний.

```csharp
string properString = "Hello World!";
Console.WriteLine(properString.ToUpper());
// This example displays the following output:
//       HELLO WORLD!
```

```vb
Dim MyString As String = "Hello World!"
Console.WriteLine(MyString.ToUpper())
' This example displays the following output:
'       HELLO WORLD!
```

## <a name="tolower"></a>ToLower

Метод [String.ToLower](xref:System.String.ToLower) аналогичен предыдущему методу, однако преобразует все символы в строке в нижний регистр. В примере ниже смешанный регистр строки "Hello World!" изменяется на нижний.

```csharp
string properString = "Hello World!";
Console.WriteLine(properString.ToLower());
// This example displays the following output:
//       hello world!
```

```vb
Dim MyString As String = "Hello World!"
Console.WriteLine(MyString.ToLower())
' This example displays the following output:
'       hello world!
```

## <a name="see-also"></a>См. также

[Базовые операции со строками](basic-string-operations.md)

