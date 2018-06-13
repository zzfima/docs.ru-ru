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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ac495e10be2ec1534dc9d9081aef369773d93e17
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33649878"
---
# <a name="-win32resource"></a>-win32resource
Вставляет файл ресурсов Win32 в выходной файл.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
-win32resource:filename  
```  
  
## <a name="arguments"></a>Аргументы  
 `filename`  
 Имя файла ресурсов, чтобы добавить в выходной файл. Заключите имя файла в кавычки (» «), если он содержит пробелы.  
  
## <a name="remarks"></a>Примечания  
 С помощью компилятора ресурсов Microsoft Windows (RC) можно создать файл ресурсов Win32.  
  
 Ресурс Win32 может содержать версию или точечный рисунок (значок) информацию, помогающую идентификации приложения в **проводнике**. Если вы не укажете `-win32resource`, компилятор создает сведения о версии на основе версии сборки. `-win32resource` И `-win32icon` являются взаимоисключающими.  
  
 В разделе [- linkresource (Visual Basic)](../../../visual-basic/reference/command-line-compiler/linkresource.md) ссылку на [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] файла ресурсов или [-ресурсов (Visual Basic)](../../../visual-basic/reference/command-line-compiler/resource.md) для присоединения [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] файла ресурсов.  
  
> [!NOTE]
>  `-win32resource` Параметр недоступен в среде разработки Visual Studio; она доступна только при компиляции из командной строки.  
  
## <a name="example"></a>Пример  
 Следующий код компилирует `In.vb` и присоединяет файл ресурсов Win32 `Rf.res`:  
  
```console  
vbc -win32resource:rf.res in.vb  
```  
  
## <a name="see-also"></a>См. также  
 [Компилятор Visual Basic с интерфейсом командной строки](../../../visual-basic/reference/command-line-compiler/index.md)  
 [Примеры командных строк компиляции](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
