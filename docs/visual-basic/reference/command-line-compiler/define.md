---
title: -Определение (Visual Basic)
ms.date: 03/10/2018
helpviewer_keywords:
- -d compiler option [Visual Basic]
- /d compiler option [Visual Basic]
- -define compiler option [Visual Basic]
- d compiler option [Visual Basic]
- /define compiler option [Visual Basic]
- define compiler option [Visual Basic]
ms.assetid: f735c57d-1cf9-4f2f-a26f-0de630fd4077
ms.openlocfilehash: c21223cc353b7a4614511aa97340c6bc5d61e70e
ms.sourcegitcommit: 41c0637e894fbcd0713d46d6ef1866f08dc321a2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/01/2019
ms.locfileid: "57200662"
---
# <a name="-define-visual-basic"></a>-Определение (Visual Basic)
Задает константы условной компиляции.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
-define:["]symbol[=value][,symbol[=value]]["]  
' -or-  
-d:["]symbol[=value][,symbol[=value]]["]  
```  
  
## <a name="arguments"></a>Аргументы  
  
|Термин|Определение|  
|---|---|  
|`symbol`|Обязательный. Определяемый символ.|  
|`value`|Необязательно. Значение, которому назначается `symbol`. Если `value` представляет собой строку, оно должно быть заключено в обратная косая черта и кавычка (\\«) кавычки. Если значение не задано, считается, что используется значение True.|  
  
## <a name="remarks"></a>Примечания  
 `-define` Параметр действует аналогично использованию `#Const` директивы препроцессора в файле исходного кода, за исключением этой константы, определенные с помощью `-define` являются общими и применяются ко всем файлам в проекте.  
  
 Вы можете использовать символы, созданные этим параметром с помощью директивы `#If`...`Then`...`#Else`, для условной компиляции исходных файлов.  
  
 `-d` является краткой формой `-define`.  
  
 Вы можете определить несколько символов с помощью `-define`, разделяя их определения запятой.  
  
|Задание параметра /define в интегрированной среде разработки Visual Studio|  
|---|  
|1.  Выберите проект в **Обозревателе решений**. В меню **Проект** выберите пункт **Свойства**. <br />2.  Откройте вкладку **Компиляция**.<br />3.  Нажмите кнопку **Дополнительно**.<br />4.  Измените значение в **настраиваемые константы** поле.|  
  
## <a name="example"></a>Пример  
 В следующем примере кода определяются и используются две константы условной компиляции.  
  
 [!code-vb[VbVbalrCompiler#45](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCompiler/VB/Class1.vb#45)]  
  
## <a name="see-also"></a>См. также
- [Компилятор Visual Basic с интерфейсом командной строки](../../../visual-basic/reference/command-line-compiler/index.md)
- [Директивы #If...Then...#Else](../../../visual-basic/language-reference/directives/if-then-else-directives.md)
- [Директива #Const](../../../visual-basic/language-reference/directives/const-directive.md)
- [Примеры командных строк компиляции](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
