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
ms.openlocfilehash: fef2652f591e713140c651a9cb0df1ea9e6236c8
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/07/2019
ms.locfileid: "72005600"
---
# <a name="-filealign"></a>-filealign
Задает выравнивание размеров выходного файла.  
  
## <a name="syntax"></a>Синтаксис  
  
```console  
-filealign:number  
```  
  
## <a name="arguments"></a>Аргументы  
 `number`  
 Обязательный. Значение, указывающее выравнивание разделов в выходном файле. Допустимые значения: 512, 1024, 2048, 4096 и 8192. Эти значения указаны в байтах.  
  
## <a name="remarks"></a>Примечания  
 Параметр `-filealign` можно использовать для указания выравнивания разделов в выходном файле. Разделы — это блоки непрерывной памяти в переносимом исполняемом (PE) файле, содержащем либо код, либо данные. Параметр `-filealign` позволяет компилировать приложение с нестандартным выравниванием; большинству разработчиков не нужно использовать этот параметр.  
  
 Каждый раздел соответствует границе, кратной значению `-filealign`. Фиксированный размер по умолчанию не предусмотрен. Если `-filealign` не указан, компилятор выбирает значение по умолчанию во время компиляции.  
  
 Указав размер раздела, можно изменить размер выходного файла. Изменение размера раздела может применяться для программ, выполняющихся на небольших устройствах.  
  
> [!NOTE]
> Параметр `-filealign` недоступен в среде разработки Visual Studio; Он доступен только при компиляции из командной строки.  
  
## <a name="see-also"></a>См. также

- [Компилятор Visual Basic с интерфейсом командной строки](../../../visual-basic/reference/command-line-compiler/index.md)
