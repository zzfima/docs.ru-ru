---
title: "Optional (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vb.Optional"
  - "vb.optional"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "Optional - ключевое слово"
  - "Optional - ключевое слово, контексты"
ms.assetid: 4571ce88-a539-4115-b230-54eb277c6aa7
caps.latest.revision: 14
caps.handback.revision: 14
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Optional (Visual Basic)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Указывает, что аргумент процедуры может быть пропущен при ее вызове.  
  
## Заметки  
 Для каждого необязательного параметра необходимо указать константное выражение в качестве значения по умолчанию.  Если выражение [Nothing](../../../visual-basic/language-reference/nothing.md), то используется значение по умолчанию для типа данных значения по умолчанию для параметра.  
  
 Если список параметров содержит необязательный параметр, то каждый параметр, который следует за ним также должен быть необязательным.  
  
 Модификатор `Optional` можно использовать в следующих контекстах:  
  
-   [Оператор Declare](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
-   [Оператор Function](../../../visual-basic/language-reference/statements/function-statement.md)  
  
-   [Оператор Property](../../../visual-basic/language-reference/statements/property-statement.md)  
  
-   [Оператор Sub](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
> [!NOTE]
>  При вызове процедуры с или без дополнительных параметров можно передать аргументы по положению или по имени.  Дополнительные сведения см. в разделе [Передача аргументов по позиции и по имени](../../../visual-basic/programming-guide/language-features/procedures/passing-arguments-by-position-and-by-name.md).  
  
> [!NOTE]
>  Можно также определить процедуру с необязательными параметрами с помощью перегружен.  Если имеется один необязательный параметр, то можно определить 2 перегруженные версии процедуры, одна из которых принимает параметр, а другая, не делает.  Дополнительные сведения см. в разделе [Перегрузка процедур](../../../visual-basic/programming-guide/language-features/procedures/procedure-overloading.md).  
  
## Пример  
 В следующем примере определяется процедуры с необязательным параметром.  
  
```  
Public Function FindMatches(ByRef values As List(Of String),  
                            ByVal searchString As String,  
                            Optional ByVal matchCase As Boolean = False) As List(Of String)  
  
    Dim results As IEnumerable(Of String)  
  
    If matchCase Then  
        results = From v In values  
                  Where v.Contains(searchString)  
    Else  
        results = From v In values  
                  Where UCase(v).Contains(UCase(searchString))  
    End If  
  
    Return results.ToList()  
End Function  
```  
  
## Пример  
 В следующем примере показано, как вызывать процедуру с аргументами, переданными по позиции и с аргументами, переданными по имени.  Процедура имеет 2 необязательных параметра.  
  
 [!code-vb[VbVbalrKeywords#21](../../../visual-basic/language-reference/codesnippet/VisualBasic/optional_1.vb)]  
  
## См. также  
 [Список параметров](../../../visual-basic/language-reference/statements/parameter-list.md)   
 [Необязательные параметры](../../../visual-basic/programming-guide/language-features/procedures/optional-parameters.md)   
 [Ключевые слова](../../../visual-basic/language-reference/keywords/index.md)