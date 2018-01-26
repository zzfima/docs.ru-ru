---
title: /define (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- -d compiler option [Visual Basic]
- /d compiler option [Visual Basic]
- -define compiler option [Visual Basic]
- d compiler option [Visual Basic]
- /define compiler option [Visual Basic]
- define compiler option [Visual Basic]
ms.assetid: f735c57d-1cf9-4f2f-a26f-0de630fd4077
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 62669ec40803170cb623382b09472b82121d26bb
ms.sourcegitcommit: 34ec7753acf76f90a0fa845235ef06663dc9e36e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="define-visual-basic"></a>/define (Visual Basic)
Задает константы условной компиляции.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
/define:["]symbol[=value][,symbol[=value]]["]  
' -or-  
/d:["]symbol[=value][,symbol[=value]]["]  
```  
  
## <a name="arguments"></a>Аргументы  
  
|Термин|Определение|  
|---|---|  
|`symbol`|Обязательный. Определяемый символ.|  
|`value`|Необязательно. Значение, которому назначается `symbol`. Если `value` представляет собой строку, оно должно быть заключено в обратная косая черта и кавычка (\\«) кавычки. Если значение не задано, считается, что используется значение True.|  
  
## <a name="remarks"></a>Примечания  
 Влияние параметра `/define` похоже на использование директивы препроцессора `#Const` в исходном файле, за исключением того, что определенные с помощью `/define` константы являются общими и применяются ко всем файлам в проекте.  
  
 Вы можете использовать символы, созданные этим параметром с помощью директивы `#If`...`Then`...`#Else`, для условной компиляции исходных файлов.  
  
 `/d` является краткой формой `/define`.  
  
 Вы можете определить несколько символов с помощью `/define`, разделяя их определения запятой.  
  
|Задание параметра /define в интегрированной среде разработки Visual Studio|  
|---|  
|1.  Выберите проект в **Обозревателе решений**. В меню **Проект** выберите пункт **Свойства**. <br />2.  Откройте вкладку **Компиляция**.<br />3.  Нажмите кнопку **Дополнительно**.<br />4.  Измените значение в **пользовательские константы** поле.|  
  
## <a name="example"></a>Пример  
 В следующем примере кода определяются и используются две константы условной компиляции.  
  
 [!code-vb[VbVbalrCompiler#45](../../../visual-basic/reference/command-line-compiler/codesnippet/VisualBasic/define_1.vb)]  
  
## <a name="see-also"></a>См. также  
 [Компилятор Visual Basic с интерфейсом командной строки](../../../visual-basic/reference/command-line-compiler/index.md)  
 [Директивы #If...Then...#Else](../../../visual-basic/language-reference/directives/if-then-else-directives.md)  
 [Директива #Const](../../../visual-basic/language-reference/directives/const-directive.md)  
 [Примеры командных строк компиляции](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
