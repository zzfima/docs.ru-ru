---
title: -netcf
ms.date: 03/13/2018
f1_keywords:
- /netcf
- -netcf
helpviewer_keywords:
- -netcf compiler option [Visual Basic]
- netcf compiler option [Visual Basic]
- /netcf compiler option [Visual Basic]
ms.assetid: db7cfa59-c315-401c-a59b-0daf355343d6
ms.openlocfilehash: 987a948d739f6b9e8e5a3e8fc6eadbfd60003723
ms.sourcegitcommit: 41c0637e894fbcd0713d46d6ef1866f08dc321a2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/01/2019
ms.locfileid: "57203062"
---
# <a name="-netcf"></a>-netcf
Задает для компилятора целевой объект [!INCLUDE[Compact](~/includes/compact-md.md)].  
  
## <a name="syntax"></a>Синтаксис  
  
```  
-netcf  
```  
  
## <a name="remarks"></a>Примечания  
 `-netcf` Компилятору Visual Basic к целевому объекту [!INCLUDE[Compact](~/includes/compact-md.md)] вместо полной [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)]. Функциональные возможности языка, которая присутствует только в полной [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] отключена.  
  
 `-netcf` Параметр предназначен для использования с [- sdkpath](../../../visual-basic/reference/command-line-compiler/sdkpath.md). Языковые возможности, отключенные по `-netcf` являются те же функции языка, не представленным в файлах `-sdkpath`.  
  
> [!NOTE]
>  `-netcf` Не доступна из среды разработки Visual Studio; она доступна только при компиляции из командной строки. `-netcf` Был установлен при загрузке проекта Visual Basic для устройства.  
  
 `-netcf` Параметр изменяет следующие функции языка:  
  
-   [Окончания \<ключевое слово > инструкции](../../../visual-basic/language-reference/statements/end-keyword-statement.md) ключевое слово, которое завершает выполнение программы, отключен. Следующая программа компилируется и выполняется без `-netcf` , но во время компиляции с `-netcf`.  
  
     [!code-vb[VbVbalrCompiler#34](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCompiler/VB/netcf.vb#34)]  
  
-   Позднее связывание, во всех формах, отключен. Ошибки времени компиляции создаются при обнаружении распознанных сценариев позднего связывания. Следующая программа компилируется и выполняется без `-netcf` , но во время компиляции с `-netcf`.  
  
     [!code-vb[VbVbalrCompiler#35](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCompiler/VB/OptionStrictOff.vb#35)]  
  
-   [Автоматически](../../../visual-basic/language-reference/modifiers/auto.md), [Ansi](../../../visual-basic/language-reference/modifiers/ansi.md), и [Юникода](../../../visual-basic/language-reference/modifiers/unicode.md) модификаторы отключены. Синтаксис [Declare Statement](../../../visual-basic/language-reference/statements/declare-statement.md) инструкции также изменяется — `Declare Sub|Function name Lib "library" [Alias "alias"] [([arglist])]`. В следующем коде показано влияние `-netcf` на процесс компиляции.  
  
     [!code-vb[VbVbalrCompiler#36](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCompiler/VB/OptionStrictOff.vb#36)]  
  
-   Использование ключевых слов Visual Basic 6.0, которые были удалены из Visual Basic создает различные ошибки при `-netcf` используется. Это влияет на сообщения об ошибках для следующих ключевых слов:  
  
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
 Следующий код компилирует `Myfile.vb` с [!INCLUDE[Compact](~/includes/compact-md.md)], с помощью версии библиотеки mscorlib.dll и Microsoft.VisualBasic.dll см. в каталог установки по умолчанию для [!INCLUDE[Compact](~/includes/compact-md.md)] на диске C:. Как правило, используется самую последнюю версию [!INCLUDE[Compact](~/includes/compact-md.md)].  
  
```console  
vbc -netcf -sdkpath:"c:\Program Files\Microsoft Visual Studio .NET 2003\CompactFrameworkSDK\v1.0.5000\Windows CE " myfile.vb  
```  
  
## <a name="see-also"></a>См. также
- [Компилятор Visual Basic с интерфейсом командной строки](../../../visual-basic/reference/command-line-compiler/index.md)
- [Примеры командных строк компиляции](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- [-sdkpath](../../../visual-basic/reference/command-line-compiler/sdkpath.md)
