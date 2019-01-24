---
title: -recurse
ms.date: 03/13/2018
helpviewer_keywords:
- /recurse compiler option [Visual Basic]
- -recurse compiler option [Visual Basic]
- recurse compiler option [Visual Basic]
ms.assetid: 84a0b670-33ae-44c4-a46a-b90388809317
ms.openlocfilehash: b108a99c799523f3eb50c075a5dc67f0648403fa
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54552337"
---
# <a name="-recurse"></a>-recurse
Компиляция файлов исходного кода во всех вложенных каталогах указанной папки или каталога проекта.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
-recurse:[dir\]file  
```  
  
## <a name="arguments"></a>Аргументы  
 `dir`  
 Необязательный параметр. Каталог, с которого будет начинаться поиск. Если не указан, поиск начинается в каталоге проекта.  
  
 `file`  
 Обязательный. Файлы для поиска. Поддерживаются подстановочные знаки.  
  
## <a name="remarks"></a>Примечания  
 Можно использовать подстановочные знаки в имени файла, чтобы скомпилировать все соответствующие файлы в каталоге проекта без использования `-recurse`. Если указано имя выходного файла, компилятор использует имя выходного файла на обработки первого входного файла. Обычно это первый файл в список скомпилированных файлов в алфавитном порядке. По этой причине лучше всего указать выходной файл с помощью `-out` параметр.  
  
> [!NOTE]
>  `-recurse` Не доступна из среды разработки Visual Studio; она доступна только при компиляции из командной строки.  
  
## <a name="example"></a>Пример  
 Следующая команда компилирует все файлы Visual Basic в текущем каталоге.  
  
```console
vbc *.vb  
```  
  
 Следующая команда компилирует все файлы Visual Basic в `Test\ABC` directory и каталогов под ним, а затем создает `Test.ABC.dll`.  
  
```console
vbc -target:library -out:Test.ABC.dll -recurse:Test\ABC\*.vb  
```  
  
## <a name="see-also"></a>См. также
- [Компилятор Visual Basic с интерфейсом командной строки](../../../visual-basic/reference/command-line-compiler/index.md)
- [-out (Visual Basic)](../../../visual-basic/reference/command-line-compiler/out.md)
- [Примеры командных строк компиляции](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
