---
title: -win32icon
ms.date: 03/13/2018
helpviewer_keywords:
- win32icon compiler option [Visual Basic]
- -win32icon compiler option [Visual Basic]
- /win32icon compiler option [Visual Basic]
ms.assetid: aecaab01-9353-46c5-941c-6edabd4eff92
ms.openlocfilehash: dc48a8f79aa04892c514917da00b8fd6489695b1
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/14/2019
ms.locfileid: "65593088"
---
# <a name="-win32icon"></a>-win32icon
Вставляет ICO-файл в выходной файл. Этот ICO-файл представляет выходной файл в **проводнике**.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
-win32icon:filename  
```  
  
## <a name="arguments"></a>Аргументы  
  
|Термин|Определение|  
|---|---|  
|`filename`|Чтобы добавить в выходной файл ICO-файл. Заключите имя файла в кавычки (» «), если он содержит пробел.|  
  
## <a name="remarks"></a>Примечания  
 ICO-файл можно создать с помощью компилятора ресурсов Microsoft Windows (RC). Компилятор ресурсов вызывается при компиляции программы Visual C++; ICO-файл создается из RC-файл. `-win32icon` И `-win32resource` параметры являются взаимно исключающими.  
  
 См. в разделе [- linkresource (Visual Basic)](../../../visual-basic/reference/command-line-compiler/linkresource.md) для ссылки на файл ресурсов .NET Framework или [-ресурсов (Visual Basic)](../../../visual-basic/reference/command-line-compiler/resource.md) вложить файл ресурсов .NET Framework. См. в разделе [-win32resource](../../../visual-basic/reference/command-line-compiler/win32resource.md) для импорта RES-файл.  
  
|Чтобы задать - win32icon в Интегрированной среде разработки Visual Studio|  
|---|  
|1.  Выберите проект в **Обозревателе решений**. В меню **Проект** выберите пункт **Свойства**. <br />2.  Перейдите на вкладку **Приложение** .<br />3.  Измените значение в **значок** поле.|  
  
## <a name="example"></a>Пример  
 Следующий код компилирует `In.vb` и присоединяет ICO-файл, `Rf.ico`.  
  
```console
vbc -win32icon:rf.ico in.vb  
```  
  
## <a name="see-also"></a>См. также

- [Компилятор Visual Basic с интерфейсом командной строки](../../../visual-basic/reference/command-line-compiler/index.md)
- [Примеры командных строк компиляции](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
