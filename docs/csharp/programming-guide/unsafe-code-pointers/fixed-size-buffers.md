---
title: "Буферы фиксированного размера (Руководство по программированию на C#) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "буферы фиксированного размера [C#]"
  - "небезопасные буферы [C#]"
  - "небезопасный код [C#], буферы фиксированного размера"
ms.assetid: 6220d454-947c-4977-ac9d-9308c6ed5051
caps.latest.revision: 31
caps.handback.revision: 31
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# Буферы фиксированного размера (Руководство по программированию на C#)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

В языке C\# для создания буфера с массивом фиксированного размера в структуре данных можно использовать оператор [fixed](../../../csharp/language-reference/keywords/fixed-statement.md).  Это полезно при работе с существующим кодом, например с кодом, написанным на других языках, ранее созданными библиотеками DLL или проектами COM.  Фиксированный массив может принимать любые атрибуты или модификаторы, допустимые для обычных членов структуры.  Единственным ограничением является то, что массив должен иметь тип `bool`, `byte`, `char`, `short`, `int`, `long`, `sbyte`, `ushort`, `uint`, `ulong`, `float` или `double`.  
  
```  
private fixed char name[30];  
```  
  
## Заметки  
 В предыдущих версиях языка C\# объявление структуры фиксированного размера в стиле C\+\+ было затруднительным, так как структура C\# с массивом не содержит элементы массива.  Вместо этого структура содержит ссылку на элементы.  
  
 В языке C\# версии 2.0 появилась возможность встраивания массива фиксированного размера в [структуру](../../../csharp/language-reference/keywords/struct.md), если он используется в блоке [небезопасного](../../../csharp/language-reference/keywords/unsafe.md) кода.  
  
 Например, до C\# 2.0 следующая `struct` имела бы размер 8 байт.  Массив `pathName` является ссылкой на выделенный в куче массив:  
  
 [!code-cs[csProgGuidePointers#19](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/fixed-size-buffers_1.cs)]  
  
 Начиная с версии 2.0 языка C\# `struct` может содержать встроенный массив.  В следующем примере массив `fixedBuffer` имеет фиксированный размер.  Для доступа к элементам такого массива используется оператор `fixed`, устанавливающий указатель на первый элемент.  Оператор `fixed` закрепляет экземпляр `fixedBuffer` в определенном месте в памяти.  
  
 [!code-cs[csProgGuidePointers#20](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/fixed-size-buffers_2.cs)]  
  
 Размер массива из 128 элементов `char` составляет 256 байт.  В буферах фиксированного размера [char](../../../csharp/language-reference/keywords/char.md) на один символ всегда приходится два байта, независимо от кодировки.  Это справедливо даже в том случае, когда буферы char маршалируются в методы API или структуры с `CharSet = CharSet.Auto` или `CharSet = CharSet.Ansi`.  Дополнительные сведения см. в разделе <xref:System.Runtime.InteropServices.CharSet>.  
  
 Еще одним распространенным массивом фиксированного размера является массив [bool](../../../csharp/language-reference/keywords/bool.md).  Элементы в массиве `bool` всегда имеют размер в один байт.  Массивы `bool` не подходят для создания битовых массивов или буферов.  
  
> [!NOTE]
>  За исключением памяти, созданной при помощи [stackalloc](../../../csharp/language-reference/keywords/stackalloc.md), компилятор C\# и среда CLR не выполняют проверку переполнения буфера безопасности.  Как и при работе с любым небезопасным кодом следует проявлять осторожность.  
  
 Небезопасные буферы отличаются от обычных массивов следующим:  
  
-   Небезопасные буферы можно использовать в небезопасном контексте.  
  
-   Небезопасные буферы это всегда векторы или одномерные массивы.  
  
-   В объявлении массива всегда должен присутствовать счетчик, такой как `char id[8]`.  При этом `char id[]` нельзя использоваться.  
  
-   Небезопасные буферы могут быть только полями экземпляра структур в небезопасном контексте.  
  
## См. также  
 [Руководство по программированию на C\#](../../../csharp/programming-guide/index.md)   
 [Небезопасный код и указатели](../../../csharp/programming-guide/unsafe-code-pointers/index.md)   
 [Оператор fixed](../../../csharp/language-reference/keywords/fixed-statement.md)   
 [Взаимодействие](../../../csharp/programming-guide/interop/interoperability.md)