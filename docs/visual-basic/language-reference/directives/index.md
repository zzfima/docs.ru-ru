---
title: Директивы
ms.date: 07/20/2015
helpviewer_keywords:
- directives, Visual Basic compiler
- Visual Basic code, directives
- directives
ms.assetid: 20d5fe65-490a-4c23-88c2-ee4f490ed762
ms.openlocfilehash: d76e10ad5ce8ad3accdc84f97146e0816048d8f3
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74343807"
---
# <a name="directives-visual-basic"></a>Директивы (Visual Basic)

В подразделах этого раздела описаны директивы компилятора исходного кода Visual Basic.  
  
## <a name="in-this-section"></a>В этом разделе  

 [Директива #Const](../../../visual-basic/language-reference/directives/const-directive.md) — Определение константы компилятора  
  
 [Директива #ExternalSource](../../../visual-basic/language-reference/directives/externalsource-directive.md) — указывает сопоставление между исходными строками и текстом, внешним по отношению к источнику  
  
 [#If... Then... #Else директивы](../../../visual-basic/language-reference/directives/if-then-else-directives.md) --компилировать выбранные блоки кода  
  
 [Директива #Region](../../../visual-basic/language-reference/directives/region-directive.md) — сворачивание и скрытие разделов кода в редакторе Visual Studio  
  
 **#Disable, #Enable** — отключение и включение конкретных предупреждений для регионов кода.  
  
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
