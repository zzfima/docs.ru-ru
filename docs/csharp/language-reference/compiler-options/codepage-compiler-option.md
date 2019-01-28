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
ms.openlocfilehash: 7cbd3ec1b2d134106c6c9429341f5603444dac27
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54693986"
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
 При компиляции одного или нескольких файлов исходного кода, не использующих кодовую страницу по умолчанию, с помощью параметра **-codepage** можно указать нужную кодовую страницу. Параметр **-codepage** применяется ко всем файлам исходного кода, включенным в компиляцию.  
  
 Если файлы исходного кода были созданы с помощью кодовой страницы, активной на компьютере, либо с помощью кодовой страницы UNICODE или UTF-8, использовать параметр **-codepage** не требуется.  
  
 Сведения о том, как найти кодовые страницы, которые поддерживаются в системе, см. на странице, посвященной функции [GetCPInfo](/windows/desktop/api/winnls/nf-winnls-getcpinfo).  
  
 Этот параметр компилятора недоступен в Visual Studio и не может быть изменен программным способом.  
  
## <a name="see-also"></a>См. также

- [Параметры компилятора C# ](../../../csharp/language-reference/compiler-options/index.md)
- [Управление свойствами проектов и решений](/visualstudio/ide/managing-project-and-solution-properties)
