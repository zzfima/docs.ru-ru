---
title: -win32icon
ms.date: 03/13/2018
helpviewer_keywords:
- win32icon compiler option [Visual Basic]
- -win32icon compiler option [Visual Basic]
- /win32icon compiler option [Visual Basic]
ms.assetid: aecaab01-9353-46c5-941c-6edabd4eff92
ms.openlocfilehash: afc35578f362f4a72a40fdb3d87406a8795cb59d
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/27/2018
ms.locfileid: "50194869"
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
