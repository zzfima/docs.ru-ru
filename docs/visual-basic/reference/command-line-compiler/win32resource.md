---
title: -win32resource
ms.date: 03/13/2018
f1_keywords:
- -win32resource
- win32resource
helpviewer_keywords:
- /win32resource compiler option [Visual Basic]
- -win32resource compiler option [Visual Basic]
- win32resource compiler option [Visual Basic]
ms.assetid: e226946d-19ce-4cc9-91f5-aed24f77aa2b
ms.openlocfilehash: d8f9c9aac87fd71b61a5413386582ae660efd903
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/14/2019
ms.locfileid: "65593071"
---
# <a name="-win32resource"></a>-win32resource
Вставляет файл ресурсов Win32 в выходной файл.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
-win32resource:filename  
```  
  
## <a name="arguments"></a>Аргументы  
 `filename`  
 Имя файла ресурсов для добавления в выходной файл. Заключите имя файла в кавычки (» «), если он содержит пробел.  
  
## <a name="remarks"></a>Примечания  
 Файл ресурсов Win32 можно создать с помощью компилятора ресурсов Microsoft Windows (RC).  
  
 Ресурс Win32 может содержать версии или точечный рисунок (значок) информацию о идентификации приложения в **проводнике**. Если вы не укажете `-win32resource`, компилятор создает сведения о версии, на основе версии сборки. `-win32resource` И `-win32icon` параметры являются взаимно исключающими.  
  
 См. в разделе [- linkresource (Visual Basic)](../../../visual-basic/reference/command-line-compiler/linkresource.md) для ссылки на файл ресурсов .NET Framework или [-ресурсов (Visual Basic)](../../../visual-basic/reference/command-line-compiler/resource.md) вложить файл ресурсов .NET Framework.  
  
> [!NOTE]
>  `-win32resource` Не доступна из среды разработки Visual Studio; она доступна только при компиляции из командной строки.  
  
## <a name="example"></a>Пример  
 Следующий код компилирует `In.vb` и присоединяет файл ресурсов Win32 `Rf.res`:  
  
```console  
vbc -win32resource:rf.res in.vb  
```  
  
## <a name="see-also"></a>См. также

- [Компилятор Visual Basic с интерфейсом командной строки](../../../visual-basic/reference/command-line-compiler/index.md)
- [Примеры командных строк компиляции](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
