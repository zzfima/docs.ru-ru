---
title: "Безопасность и поля-массивы с общим доступом только для чтения"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: security [.NET Framework], public read-only array fields
ms.assetid: 3df28dee-2a9f-40ff-9852-bfdbe59c27f3
caps.latest.revision: "7"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: ae2e9a7dd9e08344c254b52c7139c6d1dd2776a3
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="security-and-public-read-only-array-fields"></a>Безопасность и поля-массивы с общим доступом только для чтения
Никогда не используйте поля только для чтения общих массивов из управляемых библиотек для определения поведения границы или безопасности приложений, так как открытые массива только для чтения можно изменять.  
  
## <a name="remarks"></a>Примечания  
 Некоторые классы .NET framework включают только для чтения открытых полей, содержащих параметры границы конкретной платформы.  Например <xref:System.IO.Path.InvalidPathChars> представляет собой массив, описывающий символы, которые не разрешены в строке пути к файлу.  Многие аналогичные поля, присутствуют в .NET Framework.  
  
 Значения открытых полей только для чтения, например <xref:System.IO.Path.InvalidPathChars> может изменяться функцией код или код, который использует ваш код домена приложения.  Не следует использовать только для чтения массив открытые поля следующим образом для определения поведения границы приложений.  В противном случае вредоносный код можно изменить определения границ и использовании кода вами непредвиденным образом.  
  
 В версии 2.0 и более поздней версии платформы .NET Framework следует использовать методы, возвращающие новый массив, вместо того чтобы использовать массивы с общим поля.  Например, вместо использования <xref:System.IO.Path.InvalidPathChars> поля, следует использовать <xref:System.IO.Path.GetInvalidPathChars%2A> метода.  
  
 Обратите внимание, что типы .NET Framework не используют открытые поля для внутреннего определения граничных типов.  Вместо этого в .NET Framework используются отдельные закрытые поля.  Изменение значений полей с общим доступом не влияет на поведение типов .NET Framework.  
  
## <a name="see-also"></a>См. также  
 [Правила написания безопасного кода](../../../docs/standard/security/secure-coding-guidelines.md)
