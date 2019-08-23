---
title: -codepage (Visual Basic)
ms.date: 03/09/2018
helpviewer_keywords:
- -codepage compiler option [Visual Basic]
- codepage compiler option [Visual Basic]
- -codepage compiler option [Visual Basic]
ms.assetid: be36ec33-6800-4505-838c-4124564f5cc9
ms.openlocfilehash: 3a5974a910303f847679f18c23e00cfaa00caa2c
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69962613"
---
# <a name="-codepage-visual-basic"></a>-codepage (Visual Basic)
Задает кодовую страницу, используемую для всех файлов исходного кода при компиляции.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
-codepage:id  
```  
  
## <a name="arguments"></a>Аргументы  
  
|Термин|Определение|  
|---|---|  
|`id`|Обязательный. Компилятор использует кодовую страницу, заданную `id` параметром, для интерпретации кодировки исходных файлов.|  
  
## <a name="remarks"></a>Примечания  
 Для компиляции исходного кода, сохраненного с определенной кодировкой, можно `-codepage` использовать, чтобы указать, какую кодовую страницу следует использовать. `-codepage` Параметр применяется ко всем файлам исходного кода при компиляции. Дополнительные сведения см. [в разделе кодировка символов в .NET Framework](../../../standard/base-types/character-encoding.md).  
  
 Параметр `-codepage` не требуется, если файлы исходного кода были сохранены с помощью текущей кодовой страницы ANSI, Юникода или UTF-8 с подписью. Visual Studio по умолчанию сохраняет все файлы исходного кода с текущей кодовой страницей ANSI, если пользователь не задает другую кодировку в диалоговом окне **Кодировка** . Visual Studio использует диалоговое окно **Кодировка** для открытия файлов исходного кода, сохраненных с другой кодовой страницей.  
  
> [!NOTE]
> Этот `-codepage` параметр недоступен в среде разработки Visual Studio; он доступен только при компиляции из командной строки.  
  
## <a name="see-also"></a>См. также

- [Компилятор Visual Basic с интерфейсом командной строки](../../../visual-basic/reference/command-line-compiler/index.md)
