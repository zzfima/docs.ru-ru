---
title: -filealign
ms.date: 03/10/2018
helpviewer_keywords:
- sections compiler option [Visual Basic]
- alignment compiler option [Visual Basic]
- -filealign compiler option [Visual Basic]
- section alignment
- /filealign compiler option [Visual Basic]
- filealign compiler option [Visual Basic]
ms.assetid: cc61ec3d-ad38-4b28-9659-099d73cad099
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: cf9c854060e5254cedc6c1004ac3e4f25fbdbbd8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="-filealign"></a>-filealign
Задает выравнивание размеров выходного файла.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
-filealign:number  
```  
  
## <a name="arguments"></a>Аргументы  
 `number`  
 Обязательно. Значение, указывающее выравнивание разделов в выходном файле. Допустимые значения: 512, 1024, 2048, 4096 и 8192. Эти значения указаны в байтах.  
  
## <a name="remarks"></a>Примечания  
 Можно использовать `-filealign` возможность задать выравнивание разделов в выходном файле. Разделы являются блоками непрерывной памяти в Portable Executable (PE) файл с кодом или данными. `-filealign` Позволяет скомпилировать приложение с нестандартным выравниванием; большинство разработчиков не нужно использовать этот параметр.  
  
 Каждый раздел выравнивается по границе, кратной `-filealign` значение. Фиксированный размер по умолчанию не предусмотрен. Если `-filealign` не указан, компилятор выбирает значение по умолчанию во время компиляции.  
  
 Если задать размер раздела, можно изменить размер выходного файла. Изменение размера раздела может применяться для программ, выполняющихся на небольших устройствах.  
  
> [!NOTE]
>  `-filealign` Параметр недоступен в среде разработки Visual Studio; она доступна только при компиляции из командной строки.  
  
## <a name="see-also"></a>См. также  
 [Компилятор Visual Basic с интерфейсом командной строки](../../../visual-basic/reference/command-line-compiler/index.md)
