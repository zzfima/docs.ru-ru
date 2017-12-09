---
title: "-codepage (параметры компилятора C#)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords: /codepage
helpviewer_keywords:
- /codepage compiler option [C#]
- codepage compiler option [C#]
- -codepage compiler option [C#]
ms.assetid: 75942989-b69a-4308-90a0-840c73d2c478
caps.latest.revision: "15"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 1e17622256ca6a0344797ba16e007ba6feb8f873
ms.sourcegitcommit: 401c4427a3ec0d1263543033b3084039278509dc
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/06/2017
---
# <a name="codepage-c-compiler-options"></a>/codepage (параметры компилятора C#)
Этот параметр задает кодовую страницу, используемую во время компиляции, если требуемая страница не является текущей кодовой страницей системы по умолчанию.  
  
## <a name="syntax"></a>Синтаксис  
  
```console  
/codepage:id  
```  
  
## <a name="arguments"></a>Аргументы  
 `id`  
 Идентификатор кодовой страницы, используемой для всех файлов исходного кода при компиляции.  
  
## <a name="remarks"></a>Примечания  
 При компиляции одного или нескольких файлов исходного кода, не использующих кодовую страницу по умолчанию, с помощью параметра **/codepage** можно указать нужную кодовую страницу. Параметр **/codepage** применяется ко всем файлам исходного кода, включенным в компиляцию.  
  
 Если файлы исходного кода были созданы с помощью кодовой страницы, включенной на компьютере, либо с помощью кодовой страницы UNICODE или UTF-8, использовать параметр **/codepage** не требуется.  
  
 Сведения о том, как найти кодовые страницы, которые поддерживаются в системе, см. на странице, посвященной функции [GetCPInfo](https://msdn.microsoft.com/library/dd318078(VS.85).aspx).  
  
 Этот параметр компилятора недоступен в Visual Studio и не может быть изменен программным способом.  
  
## <a name="see-also"></a>См. также  
 [Параметры компилятора C# ](../../../csharp/language-reference/compiler-options/index.md)  
 [Управление свойствами проектов и решений](/visualstudio/ide/managing-project-and-solution-properties)
