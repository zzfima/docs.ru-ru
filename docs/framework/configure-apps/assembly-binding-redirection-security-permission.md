---
title: Разрешение безопасности перенаправления привязки сборок
ms.date: 03/30/2017
helpviewer_keywords:
- side-by-side execution, assembly binding redirection
- assemblies [.NET Framework], binding redirection
ms.assetid: 24a5cdff-7ed9-4195-93f3-edf6899019fc
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: ef9295028aeb7bfcc6df88e9c8bb7f80e2a31368
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="assembly-binding-redirection-security-permission"></a>Разрешение безопасности перенаправления привязки сборок
Для явного перенаправления привязки сборки в файле конфигурации приложения необходимо разрешение безопасности. Это относится к перенаправлению как сборок платформы .NET Framework, так и сторонних сборок. Разрешение можно получить, установив <xref:System.Security.Permissions.SecurityPermissionFlag> флаг <xref:System.Security.Permissions.SecurityPermission>. Управляемые сборки не имеют разрешений по умолчанию.  
  
 Разрешение безопасности к приложениям, работающим в зону надежных (локальный компьютер) и интрасеть. Приложения, выполняющиеся в зоне Интернета, строго запрещено осуществлять перенаправление привязки сборок.  
  
 Разрешение не требуется, если перенаправление сборки выполняется в файл политики издателя, которые управляются издателем компонента или в файле конфигурации компьютера, который управляется администратором. Тем не менее, требуется разрешение для приложения, чтобы явно игнорировать политику издателя с помощью [ \<исполняемым = «no» / >](../../../docs/framework/configure-apps/file-schema/runtime/publisherpolicy-element.md) в файле конфигурации приложения.  
  
 В следующей таблице показаны по умолчанию параметры безопасности для **BindingRedirects** флаг.  
  
|Зоны|Установка флага BindingRedirects|  
|----------|-----------------------------------|  
|Зоны надежных узлов (локальный компьютер)|**ON**|  
|Зоны интрасети|**ON**|  
|Зона Интернета|**OFF**|  
|Зоны без доверия|**OFF**|  
  
 Администратор может изменить эти параметры безопасности, чтобы разрешить или запретить определенные сценарии на данном компьютере. Нет средств для изменения **BindingRedirects** установку по умолчанию; флагов администратору необходимо вручную изменить файл Security.config на компьютере пользователя.  
  
## <a name="see-also"></a>См. также  
 [Файлы политики издателя и выполнения Side-by-Side](http://msdn.microsoft.com/library/97a042be-4d72-40c3-91c0-76fd36bdf133)  
 [Практическое руководство. Включение и отключение автоматического перенаправления привязки](../../../docs/framework/configure-apps/how-to-enable-and-disable-automatic-binding-redirection.md)  
 [Параллельное выполнение](../../../docs/framework/deployment/side-by-side-execution.md)
