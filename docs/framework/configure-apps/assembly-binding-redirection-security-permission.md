---
title: Разрешение безопасности перенаправления привязки сборок
ms.date: 03/30/2017
helpviewer_keywords:
- side-by-side execution, assembly binding redirection
- assemblies [.NET Framework], binding redirection
ms.assetid: 24a5cdff-7ed9-4195-93f3-edf6899019fc
ms.openlocfilehash: ba4e7e790860696f4489e9ef7b73bddcb8c4e399
ms.sourcegitcommit: b8ace47d839f943f785b89e2fff8092b0bf8f565
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2019
ms.locfileid: "55674442"
---
# <a name="assembly-binding-redirection-security-permission"></a>Разрешение безопасности перенаправления привязки сборок
Для явного перенаправления привязки сборки в файле конфигурации приложения необходимо разрешение безопасности. Это относится к перенаправлению как сборок платформы .NET Framework, так и сторонних сборок. Разрешение, задав <xref:System.Security.Permissions.SecurityPermissionFlag> флаг <xref:System.Security.Permissions.SecurityPermission>. Управляемые сборки не имеют разрешений по умолчанию.  
  
 Разрешение безопасности к приложениям, работающим в зону надежных (локальный компьютер) и зоны интрасети. Приложения, работающие в зоне Интернета, строго запрещено выполнять перенаправление привязки сборок.  
  
 Разрешение не требуется, если перенаправление сборки выполняется в файл политики издателя, которые управляются издателем компонента, или в файле конфигурации компьютера, которое управляется администратором. Тем не менее, разрешение является обязательным для приложения, чтобы явно игнорировать политику издателя с помощью [ \<исполняемым = «no» / >](../../../docs/framework/configure-apps/file-schema/runtime/publisherpolicy-element.md) элемент в файле конфигурации приложения.  
  
 В следующей таблице показаны по умолчанию параметры безопасности для **BindingRedirects** флаг.  
  
|Зона|Установка флага BindingRedirects|  
|----------|-----------------------------------|  
|Зоны надежных узлов (локальный компьютер)|**ON**|  
|Зона интрасети|**ON**|  
|Зона Интернета|**OFF**|  
|Зоны без доверия|**OFF**|  
  
 Администратор может изменить эти параметры безопасности, чтобы разрешить или запретить конкретных сценариев на данном компьютере. Нет средств по изменению **BindingRedirects** флаг, используемый по умолчанию; Azure с помощью администратора необходимо вручную изменить файл Security.config на компьютере пользователя.  
  
## <a name="see-also"></a>См. также

- [Файлы политики издателя и выполнение Side-by-Side](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/06d2bae3(v=vs.100))
- [Практическое руководство. Включение и отключение автоматического перенаправления привязки](../../../docs/framework/configure-apps/how-to-enable-and-disable-automatic-binding-redirection.md)
- [Параллельное выполнение](../../../docs/framework/deployment/side-by-side-execution.md)
