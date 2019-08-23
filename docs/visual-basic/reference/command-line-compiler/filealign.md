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
ms.openlocfilehash: 2893c1760a856a7d736e9c03ba33d9771722b5b2
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69929476"
---
# <a name="-filealign"></a>-filealign
Задает выравнивание размеров выходного файла.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
-filealign:number  
```  
  
## <a name="arguments"></a>Аргументы  
 `number`  
 Обязательный. Значение, указывающее выравнивание разделов в выходном файле. Допустимые значения: 512, 1024, 2048, 4096 и 8192. Эти значения указаны в байтах.  
  
## <a name="remarks"></a>Примечания  
 С помощью `-filealign` параметра можно указать выравнивание разделов в выходном файле. Разделы — это блоки непрерывной памяти в переносимом исполняемом (PE) файле, содержащем либо код, либо данные. `-filealign` Параметр позволяет компилировать приложение с нестандартным выравниванием; большинству разработчиков не нужно использовать этот параметр.  
  
 Каждый раздел соответствует границе, кратной `-filealign` значению. Фиксированный размер по умолчанию не предусмотрен. Если `-filealign` параметр не указан, компилятор выбирает значение по умолчанию во время компиляции.  
  
 Указав размер раздела, можно изменить размер выходного файла. Изменение размера раздела может применяться для программ, выполняющихся на небольших устройствах.  
  
> [!NOTE]
> Этот `-filealign` параметр недоступен в среде разработки Visual Studio; он доступен только при компиляции из командной строки.  
  
## <a name="see-also"></a>См. также

- [Компилятор Visual Basic с интерфейсом командной строки](../../../visual-basic/reference/command-line-compiler/index.md)
