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
ms.openlocfilehash: 551d151ab923110c73a528a5def639fb383c889f
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54715924"
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
 Можно использовать `-filealign` параметр, чтобы указать выравнивание разделов в выходном файле. Разделы являются блоками непрерывной памяти в переносимых исполняемых (PE) файл, содержащий код или данные. `-filealign` Позволяет скомпилировать приложение с нестандартным выравниванием; большинство разработчиков не обязательно должны использовать этот параметр.  
  
 Каждый раздел выравнивается по границе, кратной `-filealign` значение. Фиксированный размер по умолчанию не предусмотрен. Если `-filealign` не указан, компилятор выбирает значение по умолчанию во время компиляции.  
  
 Указывает размер раздела, можно изменить размер выходного файла. Изменение размера раздела может применяться для программ, выполняющихся на небольших устройствах.  
  
> [!NOTE]
>  `-filealign` Не доступна из среды разработки Visual Studio; она доступна только при компиляции из командной строки.  
  
## <a name="see-also"></a>См. также
- [Компилятор Visual Basic с интерфейсом командной строки](../../../visual-basic/reference/command-line-compiler/index.md)
