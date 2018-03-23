---
title: -recurse
ms.date: 03/13/2018
ms.prod: .net
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- /recurse compiler option [Visual Basic]
- -recurse compiler option [Visual Basic]
- recurse compiler option [Visual Basic]
ms.assetid: 84a0b670-33ae-44c4-a46a-b90388809317
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: bb1cc114c2882aa82787f94a271dd7684c716b01
ms.sourcegitcommit: 498799639937c89de777361aab74261efe7b79ea
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/22/2018
---
# <a name="-recurse"></a>-recurse
Компилирует файлы с исходным кодом во всех дочерних папках указанного каталога или каталога проекта.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
-recurse:[dir\]file  
```  
  
## <a name="arguments"></a>Аргументы  
 `dir`  
 Необязательный. Каталог, с которого будет начинаться поиск. Если не указан, поиск начинается в каталоге проекта.  
  
 `file`  
 Обязательно. Файлы для поиска. Поддерживаются подстановочные знаки.  
  
## <a name="remarks"></a>Примечания  
 Можно использовать подстановочные знаки в имени файла для компиляции всех файлов в каталоге проекта без использования `-recurse`. Если указано имя выходного файла, компилятор использует имя выходного файла, обработано первой входной файл. Обычно это первый файл в списке файлов, скомпилированных в алфавитном порядке. По этой причине лучше всего задать выходной файл с помощью `-out` параметр.  
  
> [!NOTE]
>  `-recurse` Параметр недоступен в среде разработки Visual Studio; она доступна только при компиляции из командной строки.  
  
## <a name="example"></a>Пример  
 Следующая команда компилирует все [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] файлы в текущем каталоге.  
  
```console
vbc *.vb  
```  
  
 Следующая команда компилирует все [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] файлы в `Test\ABC` каталога и любые каталоги под ним, а затем создает `Test.ABC.dll`.  
  
```console
vbc -target:library -out:Test.ABC.dll -recurse:Test\ABC\*.vb  
```  
  
## <a name="see-also"></a>См. также  
 [Компилятор Visual Basic с интерфейсом командной строки](../../../visual-basic/reference/command-line-compiler/index.md)  
 [-out (Visual Basic)](../../../visual-basic/reference/command-line-compiler/out.md)  
 [Примеры командных строк компиляции](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
