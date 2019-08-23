---
title: -recurse
ms.date: 03/13/2018
helpviewer_keywords:
- /recurse compiler option [Visual Basic]
- -recurse compiler option [Visual Basic]
- recurse compiler option [Visual Basic]
ms.assetid: 84a0b670-33ae-44c4-a46a-b90388809317
ms.openlocfilehash: 4281c7bf5a7972d323e1e649aaef437c7ee901ff
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69956266"
---
# <a name="-recurse"></a>-recurse
Компилирует файлы исходного кода во всех дочерних каталогах указанного каталога или каталога проекта.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
-recurse:[dir\]file  
```  
  
## <a name="arguments"></a>Аргументы  
 `dir`  
 Необязательный параметр. Каталог, с которого будет начинаться поиск. Если не указано, поиск начинается в каталоге проекта.  
  
 `file`  
 Обязательный. Файлы для поиска. Поддерживаются подстановочные знаки.  
  
## <a name="remarks"></a>Примечания  
 В имени файла можно использовать подстановочные знаки для компиляции всех соответствующих файлов в каталоге проекта без использования `-recurse`. Если имя выходного файла не указано, компилятор выводит имя выходного файла для первого обработанного входного файла. Обычно это первый файл в списке файлов, скомпилированных при просмотре в алфавитном порядке. По этой причине лучше указывать выходной файл с помощью `-out` параметра.  
  
> [!NOTE]
> Этот `-recurse` параметр недоступен в среде разработки Visual Studio; он доступен только при компиляции из командной строки.  
  
## <a name="example"></a>Пример  
 Следующая команда компилирует все файлы Visual Basic в текущем каталоге.  
  
```console
vbc *.vb  
```  
  
 Следующая команда компилирует все файлы Visual Basic в `Test\ABC` каталоге и все каталоги, а затем создает. `Test.ABC.dll`  
  
```console
vbc -target:library -out:Test.ABC.dll -recurse:Test\ABC\*.vb  
```  
  
## <a name="see-also"></a>См. также

- [Компилятор Visual Basic с интерфейсом командной строки](../../../visual-basic/reference/command-line-compiler/index.md)
- [-out (Visual Basic)](../../../visual-basic/reference/command-line-compiler/out.md)
- [Примеры командных строк компиляции](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
