---
title: "/ recurse | Документы Microsoft"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- /recurse compiler option [Visual Basic]
- -recurse compiler option [Visual Basic]
- recurse compiler option [Visual Basic]
ms.assetid: 84a0b670-33ae-44c4-a46a-b90388809317
caps.latest.revision: 12
author: stevehoag
ms.author: shoag
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
ms.openlocfilehash: fbf7d67c7f70345e62ddbb03c8626b688b5c593b
ms.lasthandoff: 03/13/2017

---
# <a name="recurse"></a>/recurse
Компилирует файлы исходного кода во всех дочерних каталогах в указанном каталоге или каталоге проекта.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
/recurse:[dir\]file  
```  
  
## <a name="arguments"></a>Аргументы  
 `dir`  
 Необязательный. Каталог, в котором следует начать поиск. Если не указан, поиск начинается в каталоге проекта.  
  
 `file`  
 Обязательный. Файлы для поиска. Допускаются подстановочные знаки.  
  
## <a name="remarks"></a>Примечания  
 Можно использовать подстановочные знаки в имени файла для компиляции всех файлов из папки проекта без использования `/recurse`. Если указано имя выходного файла, компилятор использует имя первого входного файла обработки. Обычно это первый файл в списке файлов, скомпилированных в алфавитном порядке. По этой причине лучше всего задать выходной файл с помощью `/out` параметр.  
  
> [!NOTE]
>  `/recurse` Параметр недоступен из среды разработки Visual Studio; она доступна только при компиляции из командной строки.  
  
## <a name="example"></a>Пример  
 Следующий код компилирует все [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] файлы в текущем каталоге.  
  
```  
vbc *.vb  
```  
  
 Следующий код компилирует все [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] файлы в `Test\ABC` каталога и любые каталогов ниже его и затем создает `Test.ABC.dll`.  
  
```  
vbc /target:library /out:Test.ABC.dll /recurse:Test\ABC\*.vb  
```  
  
## <a name="see-also"></a>См. также  
 [Компилятор командной строки Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)   
 [/ out (Visual Basic)](../../../visual-basic/reference/command-line-compiler/out.md)   
 [Примеры командных строк компиляции](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
