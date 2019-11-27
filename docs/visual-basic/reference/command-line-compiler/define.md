---
title: -define
ms.date: 03/10/2018
helpviewer_keywords:
- -d compiler option [Visual Basic]
- /d compiler option [Visual Basic]
- -define compiler option [Visual Basic]
- d compiler option [Visual Basic]
- /define compiler option [Visual Basic]
- define compiler option [Visual Basic]
ms.assetid: f735c57d-1cf9-4f2f-a26f-0de630fd4077
ms.openlocfilehash: fd0875f09bf3ba7211ede500aa0da45f8b7cd2c7
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74344762"
---
# <a name="-define-visual-basic"></a>-define (Visual Basic)
Задает константы условной компиляции.  
  
## <a name="syntax"></a>Синтаксис  
  
```console  
-define:["]symbol[=value][,symbol[=value]]["]  
```

или

```console  
-d:["]symbol[=value][,symbol[=value]]["]  
```  
  
## <a name="arguments"></a>Аргументы  
  
|Термин|Определение|  
|---|---|  
|`symbol`|Обязательно. Определяемый символ.|  
|`value`|Необязательный элемент. Значение, которому назначается `symbol`. Если `value` является строкой, ее необходимо заключить в кавычки или последовательности (\\") вместо кавычек. Если значение не задано, считается, что используется значение True.|  
  
## <a name="remarks"></a>Примечания  
 Параметр `-define` действует аналогично использованию директивы препроцессора `#Const` в исходном файле, за исключением того, что константы, определенные с `-define`, являются открытыми и применяются ко всем файлам в проекте.  
  
 Вы можете использовать символы, созданные этим параметром с помощью директивы `#If`...`Then`...`#Else`, для условной компиляции исходных файлов.  
  
 `-d` является короткой формой `-define`.  
  
 Вы можете определить несколько символов с помощью `-define`, разделяя их определения запятой.  
  
|Задание параметра /define в интегрированной среде разработки Visual Studio|  
|---|  
|1. Выберите проект в **Обозреватель решений**. В меню **Проект** выберите пункт **Свойства**. <br />2. Перейдите на вкладку **Компиляция** .<br />3. Нажмите кнопку **Дополнительно**.<br />4. Измените значение в поле **пользовательские константы** .|  
  
## <a name="example"></a>Пример  
 В следующем примере кода определяются и используются две константы условной компиляции.  
  
 [!code-vb[VbVbalrCompiler#45](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCompiler/VB/Class1.vb#45)]  
  
## <a name="see-also"></a>См. также

- [Компилятор Visual Basic с интерфейсом командной строки](../../../visual-basic/reference/command-line-compiler/index.md)
- [Директивы #If...Then...#Else](../../../visual-basic/language-reference/directives/if-then-else-directives.md)
- [Директива #Const](../../../visual-basic/language-reference/directives/const-directive.md)
- [Примеры командных строк компиляции](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
