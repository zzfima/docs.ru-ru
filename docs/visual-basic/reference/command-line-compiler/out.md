---
title: -out (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- /out compiler option [Visual Basic]
- -out compiler option [Visual Basic]
- out compiler option [Visual Basic]
ms.assetid: 9f148c15-0909-4cb8-a2db-777f8a8b45ae
ms.openlocfilehash: 6b005ac26e3fffad350cb4ce52f7757c9fff2ac1
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/07/2019
ms.locfileid: "72005329"
---
# <a name="-out-visual-basic"></a>-out (Visual Basic)
Задает имя выходного файла.  
  
## <a name="syntax"></a>Синтаксис  
  
```console  
-out:filename  
```  
  
## <a name="arguments"></a>Аргументы  
  
|Термин|Определение|  
|---|---|  
|`filename`|Обязательный. Имя выходного файла, создаваемого компилятором. Если имя файла содержит пробел, заключите его в кавычки ("").|  
  
## <a name="remarks"></a>Примечания  
 Укажите полное имя и расширение создаваемого файла. Если этого не сделать, exe-файл принимает имя из файла исходного кода, содержащего процедуру `Sub Main`, а имя файла. dll — из первого файла исходного кода.  
  
 Если указать имя файла без расширения EXE или DLL, компилятор автоматически добавит расширение в зависимости от значения, указанного для параметра компилятора `-target`.  
  
|Установка в интегрированной среде разработки Visual Studio|  
|---|  
|1.  Выберите проект в **Обозревателе решений**. В меню **Проект** выберите пункт **Свойства**. <br />2.  Перейдите на вкладку **Приложение** .<br />3.  Измените значение в поле **имя сборки** .|  
  
## <a name="example"></a>Пример  
 Следующий код компилирует `T2.vb` и создает выходной файл `T2.exe`.  
  
```console
vbc t2.vb -out:t3.exe  
```  
  
## <a name="see-also"></a>См. также

- [Компилятор Visual Basic с интерфейсом командной строки](../../../visual-basic/reference/command-line-compiler/index.md)
- [-Target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md)
- [Примеры командных строк компиляции](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
