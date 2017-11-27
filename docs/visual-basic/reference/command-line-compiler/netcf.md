---
title: /netcf
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- /netcf
- netcf
helpviewer_keywords:
- -netcf compiler option [Visual Basic]
- netcf compiler option [Visual Basic]
- /netcf compiler option [Visual Basic]
ms.assetid: db7cfa59-c315-401c-a59b-0daf355343d6
caps.latest.revision: "18"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 4a75573b0881af71e907a488c2b3c15db3816fc0
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="netcf"></a>/netcf
Задает для компилятора целевой объект [!INCLUDE[Compact](~/includes/compact-md.md)].  
  
## <a name="syntax"></a>Синтаксис  
  
```  
/netcf  
```  
  
## <a name="remarks"></a>Примечания  
 `/netcf` Предписывает [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] компилятору целевой [!INCLUDE[Compact](~/includes/compact-md.md)] вместо полного [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)]. Функциональные возможности языка, присутствует только в полной [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] отключена.  
  
 `/netcf` Параметр предназначен для использования с [/sdkpath](../../../visual-basic/reference/command-line-compiler/sdkpath.md). Языковые возможности, отключенные по `/netcf` являются те же функции языка, отсутствует в файлах `/sdkpath`.  
  
> [!NOTE]
>  `/netcf` Параметр недоступен в среде разработки Visual Studio; она доступна только при компиляции из командной строки. `/netcf` Параметр задан, если [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] загрузке проекта устройства.  
  
 `/netcf` Параметр изменяет следующих возможностей языка:  
  
-   [Окончания \<ключевое слово > инструкции](../../../visual-basic/language-reference/statements/end-keyword-statement.md) ключевое слово, которое завершает выполнение программы, отключено. Следующая программа компилируется и выполняется без `/netcf` , но завершается ошибкой во время компиляции с `/netcf`.  
  
     [!code-vb[VbVbalrCompiler#34](../../../visual-basic/reference/command-line-compiler/codesnippet/VisualBasic/netcf_1.vb)]  
  
-   Позднее связывание во всех формах отключено. Ошибки времени компиляции создаются при обнаружении распознаваемым сценариев позднего связывания. Следующая программа компилируется и выполняется без `/netcf` , но завершается ошибкой во время компиляции с `/netcf`.  
  
     [!code-vb[VbVbalrCompiler#35](../../../visual-basic/reference/command-line-compiler/codesnippet/VisualBasic/netcf_2.vb)]  
  
-   [Автоматически](../../../visual-basic/language-reference/modifiers/auto.md), [Ansi](../../../visual-basic/language-reference/modifiers/ansi.md), и [Юникода](../../../visual-basic/language-reference/modifiers/unicode.md) модификаторы отключены. Синтаксис [инструкции Declare](../../../visual-basic/language-reference/statements/declare-statement.md) инструкции также изменяется для `Declare Sub|Function name Lib "library" [Alias "alias"] [([arglist])]`. В следующем коде показано влияние `/netcf` на процесс компиляции.  
  
     [!code-vb[VbVbalrCompiler#36](../../../visual-basic/reference/command-line-compiler/codesnippet/VisualBasic/netcf_3.vb)]  
  
-   Использование ключевых слов Visual Basic 6.0, которые были удалены из [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] создает различные ошибки при `/netcf` используется. Это влияет на сообщения об ошибках для следующих ключевых слов:  
  
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
 Следующий код компилирует `Myfile.vb` с [!INCLUDE[Compact](~/includes/compact-md.md)], с помощью версии mscorlib.dll и Microsoft.VisualBasic.dll найден в каталоге установки по умолчанию для [!INCLUDE[Compact](~/includes/compact-md.md)] на диске C. Обычно, следует использовать самую последнюю версию [!INCLUDE[Compact](~/includes/compact-md.md)].  
  
```  
vbc /netcf /sdkpath:"c:\Program Files\Microsoft Visual Studio .NET 2003\CompactFrameworkSDK\v1.0.5000\Windows CE " myfile.vb  
```  
  
## <a name="see-also"></a>См. также  
 [Компилятор Visual Basic с интерфейсом командной строки](../../../visual-basic/reference/command-line-compiler/index.md)  
 [Примеры командных строк компиляции](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)  
 [/sdkpath](../../../visual-basic/reference/command-line-compiler/sdkpath.md)
