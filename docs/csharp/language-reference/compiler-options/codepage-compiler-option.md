---
title: -codepage (параметры компилятора C#)
ms.date: 07/20/2015
f1_keywords:
- /codepage
helpviewer_keywords:
- /codepage compiler option [C#]
- codepage compiler option [C#]
- -codepage compiler option [C#]
ms.assetid: 75942989-b69a-4308-90a0-840c73d2c478
ms.openlocfilehash: c85cd8935bcefd1353707624052b62ee982f7b07
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/19/2019
ms.locfileid: "69603048"
---
# <a name="-codepage-c-compiler-options"></a>-codepage (параметры компилятора C#)
Этот параметр задает кодовую страницу, используемую во время компиляции, если требуемая страница не является текущей кодовой страницей системы по умолчанию.  
  
## <a name="syntax"></a>Синтаксис  
  
```console  
-codepage:id  
```  
  
## <a name="arguments"></a>Аргументы  
 `id`  
 Идентификатор кодовой страницы, используемой для всех файлов исходного кода при компиляции.  
  
## <a name="remarks"></a>Примечания  
 Во-первых, компилятор будет пытаться интерпретировать все исходные файлы в кодировке UTF-8. Если кодировка файлов исходного кода отличается от UTF-8 и использует символы, отличные от 7-разрядных символов ASCII, используйте параметр **-codepage**, чтобы указать нужную кодовую страницу. Параметр **-codepage** применяется ко всем файлам исходного кода, включенным в компиляцию.  
    
 Сведения о том, как найти кодовые страницы, которые поддерживаются в системе, см. на странице, посвященной функции [GetCPInfo](/windows/desktop/api/winnls/nf-winnls-getcpinfo).  
  
 Этот параметр компилятора недоступен в Visual Studio и не может быть изменен программным способом.  
  
## <a name="see-also"></a>См. также

- [Параметры компилятора C# ](./index.md)
- [Управление свойствами проектов и решений](/visualstudio/ide/managing-project-and-solution-properties)
