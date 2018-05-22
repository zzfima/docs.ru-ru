---
title: -preferreduilang (параметры компилятора C#)
ms.date: 07/20/2015
f1_keywords:
- /preferreduilang
helpviewer_keywords:
- preferreduilang compiler option [C#]
- /preferreduilang compiler option [C#]
- -preferreduilang compiler option [C#]
ms.assetid: 68b2462f-6778-48d7-8052-62805fe8e02c
ms.openlocfilehash: 21a3baceb8a46723de1c633e415af0660bb41840
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="-preferreduilang-c-compiler-options"></a>-preferreduilang (параметры компилятора C#)
С помощью параметра компилятора `-preferreduilang` можно указать язык, на котором компилятор C# отображает выходные данные, например сообщения об ошибках.  
  
## <a name="syntax"></a>Синтаксис  
  
```console  
-preferreduilang: language  
```  
  
## <a name="arguments"></a>Аргументы  
 `language`  
 [Имя языка](https://msdn.microsoft.com/library/windows/desktop/dd318696(v=vs.85).aspx), который будет использоваться для вывода компилятора.  
  
## <a name="remarks"></a>Примечания  
 Можно использовать параметр компилятора `-preferreduilang`, чтобы указать язык, который компилятор C# должен использовать для сообщений об ошибках и других данных вывода командной строки. Если необходимый языковой пакет не установлен, вместо него используются языковые настройки операционной системы; ошибка не возникает.  
  
```csharp  
csc.exe -preferreduilang:ja-JP  
```  
  
## <a name="requirements"></a>Требования  
  
## <a name="see-also"></a>См. также  
 [Параметры компилятора C# ](../../../csharp/language-reference/compiler-options/index.md)
