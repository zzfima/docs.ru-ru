---
title: -codepage (Visual Basic)
ms.date: 03/09/2018
helpviewer_keywords:
- -codepage compiler option [Visual Basic]
- codepage compiler option [Visual Basic]
- -codepage compiler option [Visual Basic]
ms.assetid: be36ec33-6800-4505-838c-4124564f5cc9
ms.openlocfilehash: e4cdc27ab021fe055f157b78946538f2b76870e1
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/07/2019
ms.locfileid: "72002360"
---
# <a name="-codepage-visual-basic"></a>-codepage (Visual Basic)
Задает кодовую страницу, используемую для всех файлов исходного кода при компиляции.  
  
## <a name="syntax"></a>Синтаксис  
  
```console  
-codepage:id  
```  
  
## <a name="arguments"></a>Аргументы  
  
|Термин|Определение|  
|---|---|  
|`id`|Обязательный. Компилятор использует кодовую страницу, указанную `id`, для интерпретации кодировки исходных файлов.|  
  
## <a name="remarks"></a>Примечания  
 Чтобы скомпилировать исходный код, сохраненный с определенной кодировкой, можно использовать `-codepage`, чтобы указать, какую кодовую страницу следует использовать. Параметр `-codepage` применяется ко всем файлам исходного кода в компиляции. Дополнительные сведения см. [в разделе кодировка символов в .NET Framework](../../../standard/base-types/character-encoding.md).  
  
 Параметр `-codepage` не требуется, если файлы исходного кода были сохранены с помощью текущей кодовой страницы ANSI, Юникода или UTF-8 с сигнатурой. Visual Studio по умолчанию сохраняет все файлы исходного кода с текущей кодовой страницей ANSI, если пользователь не задает другую кодировку в диалоговом окне **Кодировка** . Visual Studio использует диалоговое окно **Кодировка** для открытия файлов исходного кода, сохраненных с другой кодовой страницей.  
  
> [!NOTE]
> Параметр `-codepage` недоступен в среде разработки Visual Studio; Он доступен только при компиляции из командной строки.  
  
## <a name="see-also"></a>См. также

- [Компилятор Visual Basic с интерфейсом командной строки](../../../visual-basic/reference/command-line-compiler/index.md)
