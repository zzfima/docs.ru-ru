---
title: События безопасности (трассировка событий Windows)
ms.date: 03/30/2017
helpviewer_keywords:
- security events [.NET Framework]
- ETW, security events (CLR)
ms.assetid: 0ed69f73-5c01-4514-bd63-979c6e38d41d
ms.openlocfilehash: c443bda8cdc2c6b32760e9dcba8b81a29d81660b
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/07/2020
ms.locfileid: "75715942"
---
# <a name="security-etw-events"></a>События безопасности (трассировка событий Windows)

События безопасности создаются при проверке строгого имени и проверке Authenticode.  

## <a name="strongnameverificationstart_v1-and-strongnameverificationstop_v1-events"></a>События StrongNameVerificationStart_V1 и StrongNameVerificationStop_V1  
 В таблице ниже показаны ключевое слово и уровень. (Дополнительные сведения см. в разделе [CLR ETW Keywords and Levels](clr-etw-keywords-and-levels.md).)  
  
|Ключевое слово для вызова события|Уровень|  
|-----------------------------------|-----------|  
|`SecurityKeyword` (0x400)|Информационный (4)|  
  
 В таблице ниже представлены сведения о событии.  
  
|Event|Код события|Условие вызова|  
|-----------|--------------|-----------------|  
|`StrongNameVerificationStart_V1`|181|Начало проверки строгого имени.|  
|`StrongNameVerificationStop_V1`|182|Окончание проверки строгого имени.|  
  
 В таблице ниже представлены данные события.  
  
|Имя поля|Тип данных|Описание|  
|----------------|---------------|-----------------|  
|VerificationFlags|win:UInt32|Флаги проверки.|  
|ErrorCode|win:UInt32|Код ошибки HResult.|  
|FullyQualifiedAssemblyName|win:UnicodeString|Полное имя сборки.|  
|ClrInstanceID|win:UInt16|Уникальный идентификатор экземпляра CLR или CoreCLR.|  

## <a name="authenticodeverificationstart_v1-and-authenticodeverificationstop_v1-events"></a>События AuthenticodeVerificationStart_V1 и AuthenticodeVerificationStop_V1  
 В таблице ниже показаны ключевое слово и уровень.  
  
|Ключевое слово для вызова события|Уровень|  
|-----------------------------------|-----------|  
|`SecurityKeyword` (0x400)|Информационный (4)|  
  
 В таблице ниже представлены сведения о событии.  
  
|Event|Код события|Условие вызова|  
|-----------|--------------|-----------------|  
|`AuthenticodeVerificationStart_V1`|183|Начало проверки Authenticode.|  
|`AuthenticodeVerificationStop_V1`|184|Окончание проверки Authenticode.|  
  
 В таблице ниже представлены данные события.  
  
|Имя поля|Тип данных|Описание|  
|----------------|---------------|-----------------|  
|VerificationFlags|win:UInt32|Флаги проверки.|  
|ErrorCode|win:UInt32|Код ошибки HResult.|  
|ModulePath|win:UnicodeString|Путь к модулю.|  
|ClrInstanceID|win:UInt16|Уникальный идентификатор экземпляра CLR или CoreCLR.|  
  
## <a name="see-also"></a>См. также:

- [События трассировки событий Windows в среде CLR](clr-etw-events.md)
