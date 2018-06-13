---
title: -out (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- /out compiler option [Visual Basic]
- -out compiler option [Visual Basic]
- out compiler option [Visual Basic]
ms.assetid: 9f148c15-0909-4cb8-a2db-777f8a8b45ae
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 234071d043b2649e2438ed20fe044fb89cdb9bf8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33655893"
---
# <a name="-out-visual-basic"></a>-out (Visual Basic)
Задает имя выходного файла.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
-out:filename  
```  
  
## <a name="arguments"></a>Аргументы  
  
|Термин|Определение|  
|---|---|  
|`filename`|Обязательно. Создает имя файла выходных данных компилятора. Если имя файла содержит пробелы, заключите имя в кавычки (» «).|  
  
## <a name="remarks"></a>Примечания  
 Укажите полное имя и расширение файла для создания. Если этого не сделать, файл .exe планка файл исходного кода, содержащий `Sub Main` процедуры и DLL-файла будет использовано имя первого файла исходного кода.  
  
 Если указать имя файла без расширения .exe или .dll, компилятор автоматически добавляет расширение, в зависимости от значения, указанные для `-target` параметр компилятора.  
  
|Чтобы задать - помещает в среде разработки Visual Studio|  
|---|  
|1.  Выберите проект в **Обозревателе решений**. В меню **Проект** выберите пункт **Свойства**. <br />2.  Перейдите на вкладку **Приложение** .<br />3.  Измените значение в **имя сборки** поле.|  
  
## <a name="example"></a>Пример  
 Следующий код компилирует `T2.vb` и создает выходной файл `T2.exe`.  
  
```console
vbc t2.vb -out:t3.exe  
```  
  
## <a name="see-also"></a>См. также  
 [Компилятор Visual Basic с интерфейсом командной строки](../../../visual-basic/reference/command-line-compiler/index.md)  
 [-target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md)  
 [Примеры командных строк компиляции](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
