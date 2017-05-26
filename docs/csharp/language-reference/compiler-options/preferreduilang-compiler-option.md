---
title: "/preferreduilang (параметры компилятора C#) | Документы Майкрософт"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- /preferreduilang
dev_langs:
- CSharp
helpviewer_keywords:
- preferreduilang compiler option [C#]
- /preferreduilang compiler option [C#]
- -preferreduilang compiler option [C#]
ms.assetid: 68b2462f-6778-48d7-8052-62805fe8e02c
caps.latest.revision: 15
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Human Translation
ms.sourcegitcommit: 400dfda51d978f35c3995f90840643aaff1b9c13
ms.openlocfilehash: 0fd8ccca016b598b14780ac6cd2190442777fb53
ms.contentlocale: ru-ru
ms.lasthandoff: 03/24/2017

---
# <a name="preferreduilang-c-compiler-options"></a>/preferreduilang (параметры компилятора C#)
С помощью параметра компилятора `/preferreduilang` можно указать язык, на котором компилятор C# отображает выходные данные, например сообщения об ошибках.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
/preferreduilang: language  
```  
  
## <a name="arguments"></a>Аргументы  
 `language`  
 [Имя языка](http://go.microsoft.com/fwlink/p/?LinkId=236992), который будет использоваться для вывода компилятора.  
  
## <a name="remarks"></a>Примечания  
 Можно использовать параметр компилятора `/preferreduilang`, чтобы указать язык, который компилятор C# должен использовать для сообщений об ошибках и других данных вывода командной строки. Если необходимый языковой пакет не установлен, вместо него используются языковые настройки операционной системы; ошибка не возникает.  
  
```csharp  
csc.exe /preferreduilang:ja-JP  
```  
  
## <a name="requirements"></a>Требования  
  
## <a name="see-also"></a>См. также  
 [Параметры компилятора C# ](../../../csharp/language-reference/compiler-options/index.md)
