---
title: /recurse
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- /recurse compiler option [Visual Basic]
- -recurse compiler option [Visual Basic]
- recurse compiler option [Visual Basic]
ms.assetid: 84a0b670-33ae-44c4-a46a-b90388809317
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: bb69c7c44dcc2e8da5eb8a76f7d22f936a6d948f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="recurse"></a>/recurse
Компилирует файлы с исходным кодом во всех дочерних папках указанного каталога или каталога проекта.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
/recurse:[dir\]file  
```  
  
## <a name="arguments"></a>Аргументы  
 `dir`  
 Необязательно. Каталог, с которого будет начинаться поиск. Если не указан, поиск начинается в каталоге проекта.  
  
 `file`  
 Обязательный. Файлы для поиска. Поддерживаются подстановочные знаки.  
  
## <a name="remarks"></a>Примечания  
 Можно использовать подстановочные знаки в имени файла для компиляции всех файлов в каталоге проекта без использования `/recurse`. Если указано имя выходного файла, компилятор использует имя выходного файла, обработано первой входной файл. Обычно это первый файл в списке файлов, скомпилированных в алфавитном порядке. По этой причине лучше всего задать выходной файл с помощью `/out` параметр.  
  
> [!NOTE]
>  `/recurse` Параметр недоступен в среде разработки Visual Studio; она доступна только при компиляции из командной строки.  
  
## <a name="example"></a>Пример  
 Следующий код компилирует все [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] файлы в текущем каталоге.  
  
```  
vbc *.vb  
```  
  
 Следующий код компилирует все [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] файлы в `Test\ABC` каталога и любые каталоги под ним, а затем создает `Test.ABC.dll`.  
  
```  
vbc /target:library /out:Test.ABC.dll /recurse:Test\ABC\*.vb  
```  
  
## <a name="see-also"></a>См. также  
 [Компилятор Visual Basic с интерфейсом командной строки](../../../visual-basic/reference/command-line-compiler/index.md)  
 [/ out (Visual Basic)](../../../visual-basic/reference/command-line-compiler/out.md)  
 [Примеры командных строк компиляции](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
