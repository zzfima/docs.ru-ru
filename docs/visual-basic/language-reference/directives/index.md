---
title: Директивы
ms.date: 07/20/2015
helpviewer_keywords:
- directives, Visual Basic compiler
- Visual Basic code, directives
- directives
ms.assetid: 20d5fe65-490a-4c23-88c2-ee4f490ed762
ms.openlocfilehash: b5e857198351b30c0d7a38dce1a9e6d1209b5258
ms.sourcegitcommit: a4f9b754059f0210e29ae0578363a27b9ba84b64
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/05/2019
ms.locfileid: "74838147"
---
# <a name="directives-visual-basic"></a>Директивы (Visual Basic)

В подразделах этого раздела описаны директивы компилятора исходного кода Visual Basic.  
  
## <a name="in-this-section"></a>Содержание  

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
  