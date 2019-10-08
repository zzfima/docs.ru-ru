---
title: -win32icon
ms.date: 03/13/2018
helpviewer_keywords:
- win32icon compiler option [Visual Basic]
- -win32icon compiler option [Visual Basic]
- /win32icon compiler option [Visual Basic]
ms.assetid: aecaab01-9353-46c5-941c-6edabd4eff92
ms.openlocfilehash: 6b4b69d227c857442de6857fac023090b3698e81
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/07/2019
ms.locfileid: "72004644"
---
# <a name="-win32icon"></a>-win32icon
Вставляет ICO файл в выходной файл. Этот ICO файл представляет выходной файл в **проводнике**.  
  
## <a name="syntax"></a>Синтаксис  
  
```console  
-win32icon:filename  
```  
  
## <a name="arguments"></a>Аргументы  
  
|Термин|Определение|  
|---|---|  
|`filename`|ICO файл, добавляемый в выходной файл. Заключите имя файла в кавычки (""), если оно содержит пробел.|  
  
## <a name="remarks"></a>Примечания  
 Вы можете создать ICO-файл с помощью компилятора ресурсов Microsoft Windows (RC). Компилятор ресурсов вызывается при компиляции визуальной C++ программы; ICO-файл создается из файла. rc. Параметры `-win32icon` и `-win32resource` являются взаимоисключающими.  
  
 Чтобы присоединить файл ресурсов .NET Framework, см. раздел [-linkresource (Visual Basic)](../../../visual-basic/reference/command-line-compiler/linkresource.md) для ссылки на файл ресурсов .NET Framework или [-Resource (Visual Basic)](../../../visual-basic/reference/command-line-compiler/resource.md) . Чтобы импортировать RES-файл, см. [win32resource](../../../visual-basic/reference/command-line-compiler/win32resource.md) .  
  
|Установка параметра-win32icon в интегрированной среде разработки Visual Studio|  
|---|  
|1.  Выберите проект в **Обозревателе решений**. В меню **Проект** выберите пункт **Свойства**. <br />2.  Перейдите на вкладку **Приложение** .<br />3.  Измените значение в поле **значок** .|  
  
## <a name="example"></a>Пример  
 Следующий код компилирует `In.vb` и прикрепляет файл ICO, `Rf.ico`.  
  
```console
vbc -win32icon:rf.ico in.vb  
```  
  
## <a name="see-also"></a>См. также

- [Компилятор Visual Basic с интерфейсом командной строки](../../../visual-basic/reference/command-line-compiler/index.md)
- [Примеры командных строк компиляции](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
