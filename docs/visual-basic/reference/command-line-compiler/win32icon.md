---
title: -win32icon
ms.date: 03/13/2018
helpviewer_keywords:
- win32icon compiler option [Visual Basic]
- -win32icon compiler option [Visual Basic]
- /win32icon compiler option [Visual Basic]
ms.assetid: aecaab01-9353-46c5-941c-6edabd4eff92
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 045e621f0104c4c958d77d2443c1524b33410b7a
ms.sourcegitcommit: f6343b070f3c66877338a05c8bfb0be9985255e2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/24/2018
ms.locfileid: "39221027"
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
  
 См. в разделе [- linkresource (Visual Basic)](../../../visual-basic/reference/command-line-compiler/linkresource.md) ссылка [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] файл ресурсов или [-ресурсов (Visual Basic)](../../../visual-basic/reference/command-line-compiler/resource.md) для присоединения [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] файла ресурсов. См. в разделе [-win32resource](../../../visual-basic/reference/command-line-compiler/win32resource.md) для импорта RES-файл.  
  
|Чтобы задать - win32icon в Интегрированной среде разработки Visual Studio|  
|---|  
|1.  Выберите проект в **Обозревателе решений**. В меню **Проект** выберите пункт **Свойства**. <br />2.  Перейдите на вкладку **Приложение** .<br />3.  Измените значение в **значок** поле.|  
  
## <a name="example"></a>Пример  
 Следующий код компилирует `In.vb` и присоединяет ICO-файл, `Rf.ico`.  
  
```console
vbc -win32icon:rf.ico in.vb  
```  
  
## <a name="see-also"></a>См. также  
 [Компилятор Visual Basic с интерфейсом командной строки](../../../visual-basic/reference/command-line-compiler/index.md)  
 [Примеры командных строк компиляции](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
