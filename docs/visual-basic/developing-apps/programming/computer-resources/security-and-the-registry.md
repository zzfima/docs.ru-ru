---
title: "Безопасность и реестр (Visual Basic) | Документы Майкрософт"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- security [Visual Basic], registry
- registry, security issues
ms.assetid: 9980aff7-2f69-492b-8f66-29a9a76d3df5
caps.latest.revision: 17
author: dotnet-bot
ms.author: dotnetcontent
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
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 506271ec92eaf26409b7b380d12f6ae0622f9f90
ms.contentlocale: ru-ru
ms.lasthandoff: 05/22/2017

---
# <a name="security-and-the-registry-visual-basic"></a>Безопасность и реестр (Visual Basic)
На этой странице обсуждается, как хранение данных в реестре сказывается на безопасности.  
  
## <a name="permissions"></a>Разрешения  
 Хранить секретные данные, например пароли, в реестре обычным текстом небезопасно, даже если раздел реестра защищен ACL (списком управления доступом).  
  
 Работа с реестром может привести к нарушению безопасности, допуская несанкционированный доступ к системным ресурсам или защищенной информации. Чтобы использовать эти свойства, необходимо иметь разрешения на чтение и запись в перечислении <xref:System.Security.Permissions.RegistryPermissionAccess>, которое управляет доступом к переменным реестра. Любой код, выполняющийся с полным доверием (в рамках политики безопасности по умолчанию это любой код, установленный на локальном жестком диске компьютера пользователя), имеет необходимые разрешения для доступа к реестру. Дополнительные сведения см. в разделе о классе <xref:System.Security.Permissions.RegistryPermission>.  
  
 Переменные реестра не следует хранить в областях памяти, к которым имеет доступ код без разрешений <xref:System.Security.Permissions.RegistryPermission>. Аналогичным образом, при предоставлении разрешений следует предоставлять минимальный уровень разрешений, необходимый для выполнения задачи.  
  
 Значения разрешений на доступ к реестру определяются перечислением <xref:System.Security.Permissions.RegistryPermissionAccess>. Его члены подробно рассмотрены в следующей таблице.  
  
|Значение|Доступ к переменным реестра|  
|-----------|----------------------------------|  
|`AllAccess`|Создание, чтение и запись|  
|`Create`|Создать|  
|`NoAccess`|Доступ отсутствует|  
|`Read`|Чтение|  
|`Write`|Write|  
  
## <a name="checking-values-in-registry-keys"></a>Проверка значений в разделах реестра  
 Создавая значение реестра, необходимо решить, что делать, если это значение уже существует. Другой процесс (возможно, вредоносный) мог уже создать это значение и получить к нему доступ. Данные, добавленные в значение реестра, становятся доступными для другого процесса. Чтобы этого избежать, используйте метод `GetValue`. Он возвращает `Nothing`, если данный раздел еще не существует.  
  
> [!IMPORTANT]
>  При чтении реестра из веб-приложения идентификация текущего пользователя зависит от проверки подлинности и олицетворения, реализованных в веб-приложении.  
  
## <a name="see-also"></a>См. также  
 <xref:Microsoft.VisualBasic.MyServices.RegistryProxy>   
 [Чтение данных из реестра и запись в реестр](../../../../visual-basic/developing-apps/programming/computer-resources/reading-from-and-writing-to-the-registry.md)
