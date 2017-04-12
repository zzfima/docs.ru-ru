---
title: "/ netcf | Документы Microsoft"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- /netcf
- netcf
dev_langs:
- VB
helpviewer_keywords:
- -netcf compiler option [Visual Basic]
- netcf compiler option [Visual Basic]
- /netcf compiler option [Visual Basic]
ms.assetid: db7cfa59-c315-401c-a59b-0daf355343d6
caps.latest.revision: 18
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: d8e2328eb5434ea0e73238709c429975ae29e6d0
ms.lasthandoff: 03/13/2017

---
# <a name="netcf"></a>/netcf
Задает для компилятора целевой объект [!INCLUDE[Compact](../../../visual-basic/reference/command-line-compiler/includes/compact_md.md)].  
  
## <a name="syntax"></a>Синтаксис  
  
```  
/netcf  
```  
  
## <a name="remarks"></a>Примечания  
 `/netcf` Предписывает [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] компилятору целевой [!INCLUDE[Compact](../../../visual-basic/reference/command-line-compiler/includes/compact_md.md)] вместо полного [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)]. Функциональность языка, имеющаяся только в полной [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] отключена.  
  
 `/netcf` Параметр предназначен для использования с [/sdkpath](../../../visual-basic/reference/command-line-compiler/sdkpath.md). Языковые возможности, отключенные с `/netcf` же не присутствует в файлах с языковыми возможностями `/sdkpath`.  
  
> [!NOTE]
>  `/netcf` Параметр недоступен из среды разработки Visual Studio; она доступна только при компиляции из командной строки. `/netcf` Параметр задается при [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] загрузке проекта устройства.  
  
 `/netcf` Параметр изменяет следующие функции языка:  
  
-   [End \<ключевое слово настроек инструкции](../../../visual-basic/language-reference/statements/end-keyword-statement.md) ключевое слово, которое прекращает выполнение программы, отключено. Следующая программа компилируется и выполняется без `/netcf` , но во время компиляции с `/netcf`.  
  
     [!code-vb[VbVbalrCompiler&#34;](../../../visual-basic/reference/command-line-compiler/codesnippet/VisualBasic/netcf_1.vb)]  
  
-   Позднее связывание во всех формах отключено. При обнаружении распознанных сценариев позднего связывания, возникают ошибки во время компиляции. Следующая программа компилируется и выполняется без `/netcf` , но во время компиляции с `/netcf`.  
  
     [!code-vb[VbVbalrCompiler&#35;](../../../visual-basic/reference/command-line-compiler/codesnippet/VisualBasic/netcf_2.vb)]  
  
-   [Автоматически](../../../visual-basic/language-reference/modifiers/auto.md), [Ansi](../../../visual-basic/language-reference/modifiers/ansi.md), и [Юникода](../../../visual-basic/language-reference/modifiers/unicode.md) модификаторы отключены. Синтаксис [Declare Statement](../../../visual-basic/language-reference/statements/declare-statement.md) инструкции также изменяется — `Declare Sub|Function name Lib "library" [Alias "alias"] [([arglist])]`. В следующем коде показано влияние `/netcf` на процесс компиляции.  
  
     [!code-vb[VbVbalrCompiler&#36;](../../../visual-basic/reference/command-line-compiler/codesnippet/VisualBasic/netcf_3.vb)]  
  
-   Использование ключевых слов Visual Basic 6.0, которые были удалены из [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] создает различные ошибки при `/netcf` используется. Это влияет на сообщения об ошибках для следующих ключевых слов:  
  
    -   `Open`  
  
    -   `Close`  
  
    -   `Put`  
  
    -   `Print`  
  
    -   `Write`  
  
    -   `Input`  
  
    -   `Lock`  
  
    -   `Unlock`  
  
    -   `Seek`  
  
    -   `Width`  
  
    -   `Name`  
  
    -   `FreeFile`  
  
    -   `EOF`  
  
    -   `Loc`  
  
    -   `LOF`  
  
    -   `Line`  
  
## <a name="example"></a>Пример  
 Следующий код компилирует `Myfile.vb` с [!INCLUDE[Compact](../../../visual-basic/reference/command-line-compiler/includes/compact_md.md)], с помощью версии Mscorlib.dll и Microsoft.VisualBasic.dll найти в каталоге установки по умолчанию [!INCLUDE[Compact](../../../visual-basic/reference/command-line-compiler/includes/compact_md.md)] на диске C:. Как правило, используется последней версии [!INCLUDE[Compact](../../../visual-basic/reference/command-line-compiler/includes/compact_md.md)].  
  
```  
vbc /netcf /sdkpath:"c:\Program Files\Microsoft Visual Studio .NET 2003\CompactFrameworkSDK\v1.0.5000\Windows CE " myfile.vb  
```  
  
## <a name="see-also"></a>См. также  
 [Компилятор командной строки Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)   
 [Примеры командных строк компиляции](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)   
 [/sdkpath](../../../visual-basic/reference/command-line-compiler/sdkpath.md)
