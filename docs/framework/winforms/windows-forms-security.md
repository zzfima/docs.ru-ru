---
title: "Безопасность Windows Forms"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- designer access security [Windows Forms]
- permissions [Windows Forms], Windows Forms
- Windows Forms, security
- security [Windows Forms]
- access control [Windows Forms], Windows Forms
- security policy [Windows Forms], Windows Forms
ms.assetid: 932d438a-5285-46d8-a958-8c93d0ad6cae
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 8bd9b87fdfa54a6f9bf53e4fa897106257b4c625
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/19/2018
---
# <a name="windows-forms-security"></a>Безопасность Windows Forms
Windows Forms представляют модель безопасности, основанная на коде (безопасности уровни заданы для кода, независимо от того, пользователь, запускающий код). Это дополнение всем схемам безопасности, которые могут быть выполнены уже на компьютерах пользователей. Сюда могут относиться в браузере (например, безопасность на основе зон в Internet Explorer) или для операционной системы (например, безопасность Windows NT, основанная на учетных данных).  
  
## <a name="in-this-section"></a>В этом разделе  
 [Общие сведения о безопасности в Windows Forms](../../../docs/framework/winforms/security-in-windows-forms-overview.md)  
 Краткое описание модели безопасности .NET Framework и основные шаги, необходимые для обеспечения в приложении Windows Forms являются безопасными.  
  
 [Более безопасный доступ к файлам и данным в Windows Forms](../../../docs/framework/winforms/more-secure-file-and-data-access-in-windows-forms.md)  
 Описывает, как получить доступ к файлам и данным в среде с частичным доверием.  
  
 [Более безопасная печать в Windows Forms](../../../docs/framework/winforms/more-secure-printing-in-windows-forms.md)  
 Описывает, как получить доступ к возможностям печати в среде с частичным доверием.  
  
 [Дополнительные вопросы безопасности в формах Windows Forms](../../../docs/framework/winforms/additional-security-considerations-in-windows-forms.md)  
 Описание способов работы с окнами с помощью буфера обмена и вызова неуправляемого кода в среде с частичным доверием.  
  
## <a name="related-sections"></a>Связанные разделы  
 [NIB: Политика безопасности по умолчанию](http://msdn.microsoft.com/library/2c086873-0894-4f4d-8f7e-47427c1a3b55)  
 Перечисляет разрешения по умолчанию в наборах разрешений полного доверия, локальной интрасети и Интернета.  
  
 [NIB: Общее администрирование политики безопасности](http://msdn.microsoft.com/library/5121fe35-f0e3-402c-94ab-4f35b0a87b4b)  
 Предоставляет сведения об администрировании политики безопасности .NET Framework и повышению разрешений.  
  
 [Опасные разрешения и администрирование политик](../../../docs/framework/misc/dangerous-permissions-and-policy-administration.md)  
 Рассматриваются некоторые из разрешений.NET Framework, которые потенциально могут позволить обойти систему безопасности.  
  
 [Правила написания безопасного кода](../../../docs/standard/security/secure-coding-guidelines.md)  
 Ссылки на разделы, где приводятся рекомендации по написанию безопасного кода для .NET Framework.  
  
 [NIB: Запрос прав доступа](http://msdn.microsoft.com/library/0447c49d-8cba-45e4-862c-ff0b59bebdc2)  
 Описывает использование атрибутов, чтобы сообщить среде выполнения разрешения, необходимые для запуска для вашего кода.  
  
 [Основные понятия безопасности](../../../docs/standard/security/key-security-concepts.md)  
 Ссылки на разделы, посвященные основным аспектам безопасности кода.  
  
 [Основы управления доступом для кода](../../../docs/framework/misc/code-access-security-basics.md)  
 Описывает основы работы с политикой безопасности времени выполнения .NET Framework.  
  
 [NIB: Определение необходимости изменения политики безопасности](http://msdn.microsoft.com/library/af749b17-e461-409d-84b9-a3d44789db16)  
 Объясняется, как определить, когда приложения, для которых нужно из политики безопасности по умолчанию.  
  
 [NIB: Развертывание политики безопасности](http://msdn.microsoft.com/library/f936c1e5-033b-4bd9-a3bd-a39ba733a681)  
 Обсуждение наилучших способов развертывания изменений политики безопасности.
