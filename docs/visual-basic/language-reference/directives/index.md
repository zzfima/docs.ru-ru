---
title: Директивы (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- directives, Visual Basic compiler
- Visual Basic code, directives
- directives
ms.assetid: 20d5fe65-490a-4c23-88c2-ee4f490ed762
ms.openlocfilehash: 38d54feae5cf7bf41a825d1f6000811e2b56f319
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/01/2018
ms.locfileid: "43409191"
---
# <a name="directives-visual-basic"></a>Директивы (Visual Basic)
В подразделах этого раздела описаны директивы компилятора исходного кода Visual Basic.  
  
## <a name="in-this-section"></a>В этом разделе  
 [#Const-директива](../../../visual-basic/language-reference/directives/const-directive.md) — определение константы компилятора  
  
 [Директива #ExternalSource](../../../visual-basic/language-reference/directives/externalsource-directive.md) --сопоставления между строками источника и текста, внешним по отношению к источнику  
  
 [#If... Then... #Else директивы](../../../visual-basic/language-reference/directives/if-then-else-directives.md) — компиляция выбранных блоков кода  
  
 [Директива #Region](../../../visual-basic/language-reference/directives/region-directive.md) — Сворачивание и скрытие частей кода в редакторе Visual Studio  
  
 **#Disable, #Enable** — отключение и включение конкретных предупреждений для областей кода.  
  
```vb  
#Disable Warning BC42356 ' suppress warning about no awaits in this method  
    Async Function TestAsync() As Task  
        Console.WriteLine("testing")  
    End Function  
#Enable Warning BC42356  
```  
  
 Можно также отключить и включить список кодов предупреждений с разделителями-запятыми.  
  
## <a name="related-sections"></a>Связанные разделы  
 [Справочник по языку Visual Basic](../../../visual-basic/language-reference/index.md)  
  
 [Visual Basic](../../../visual-basic/index.md)
