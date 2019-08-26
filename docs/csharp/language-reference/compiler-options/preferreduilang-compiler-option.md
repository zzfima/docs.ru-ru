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
ms.openlocfilehash: 7ebafcf446c9033c93e0c5fa5e11ea2930bd2e1e
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/19/2019
ms.locfileid: "69602557"
---
# <a name="-preferreduilang-c-compiler-options"></a>-preferreduilang (параметры компилятора C#)
С помощью параметра компилятора `-preferreduilang` можно указать язык, на котором компилятор C# отображает выходные данные, например сообщения об ошибках.  
  
## <a name="syntax"></a>Синтаксис  
  
```console  
-preferreduilang: language  
```  
  
## <a name="arguments"></a>Аргументы  
 `language`  
 [Имя языка](/windows/desktop/Intl/language-names), который будет использоваться для вывода компилятора.  
  
## <a name="remarks"></a>Примечания  
 Можно использовать параметр компилятора `-preferreduilang`, чтобы указать язык, который компилятор C# должен использовать для сообщений об ошибках и других данных вывода командной строки. Если необходимый языковой пакет не установлен, вместо него используются языковые настройки операционной системы; ошибка не возникает.  
  
```csharp  
csc.exe -preferreduilang:ja-JP  
```  
  
## <a name="requirements"></a>Требования  
  
## <a name="see-also"></a>См. также

- [Параметры компилятора C# ](./index.md)
