---
title: Практическое руководство. Сохранение и восстановление свойств области определения приложения в сеансах приложения
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- application-scope properties [WPF], persisting
- persisting application-scope properties [WPF]
- properties [WPF], persisting
- restoring application-scope properties [WPF]
- properties [WPF], restoring
- application-scope properties [WPF], restoring
ms.assetid: 55d5904a-f444-4eb5-abd3-6bc74dd14226
ms.openlocfilehash: d9c2dda2745e7528902b6b1c4f46d17264d1a8d8
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/21/2019
ms.locfileid: "69666726"
---
# <a name="how-to-persist-and-restore-application-scope-properties-across-application-sessions"></a><span data-ttu-id="4d645-102">Практическое руководство. Сохранение и восстановление свойств области определения приложения в сеансах приложения</span><span class="sxs-lookup"><span data-stu-id="4d645-102">How to: Persist and Restore Application-Scope Properties Across Application Sessions</span></span>
<span data-ttu-id="4d645-103">В этом примере показано, как сохранять свойства области приложения при завершении работы приложения, а также как восстановить свойства области приложения при следующем запуске приложения.</span><span class="sxs-lookup"><span data-stu-id="4d645-103">This example shows how to persist application-scope properties when an application shuts down, and how to restore application-scope properties when an application is next launch.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4d645-104">Пример</span><span class="sxs-lookup"><span data-stu-id="4d645-104">Example</span></span>  
 <span data-ttu-id="4d645-105">Приложение сохраняет свойства области приложения в и восстанавливает их из изолированного хранилища.</span><span class="sxs-lookup"><span data-stu-id="4d645-105">The application persists application-scope properties to, and restores them from, isolated storage.</span></span> <span data-ttu-id="4d645-106">Изолированное хранилище — это защищенная область хранения, которая может безопасно использоваться приложениями без разрешения на доступ к файлам.</span><span class="sxs-lookup"><span data-stu-id="4d645-106">Isolated storage is a protected storage area that can safely be used by applications without file access permission.</span></span>  <span data-ttu-id="4d645-107">Файл *app. XAML* определяет `App_Startup` метод как обработчик для <xref:System.Windows.Application.Startup?displayProperty=nameWithType> события, а `App_Exit` метод — как обработчик для <xref:System.Windows.Application.Exit?displayProperty=nameWithType> события, как показано в выделенных строках первого примера.</span><span class="sxs-lookup"><span data-stu-id="4d645-107">The *App.xaml* file defines the `App_Startup` method as the handler for the <xref:System.Windows.Application.Startup?displayProperty=nameWithType> event, and the `App_Exit` method as the handler for the  <xref:System.Windows.Application.Exit?displayProperty=nameWithType> event, as shown in the highlighted lines of the first example.</span></span> <span data-ttu-id="4d645-108">Во втором примере показана часть файлов *app.XAML.CS* и *app. XAML. vb* , которая выделяет `App_Startup` код для метода, который восстанавливает свойства области приложения, и `App_Exit` метод, сохраняющий область приложения. свойства.</span><span class="sxs-lookup"><span data-stu-id="4d645-108">The second example shows a portion of the *App.xaml.cs* and *App.xaml.vb* files that highlights the code for the `App_Startup` method, which restores application-scope properties, and the `App_Exit` method, which saves application-scope properties.</span></span>

 [!code-xaml[HOWTOApplicationModelSnippets#PersistRestoreAppScopePropertiesXAML1](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTOApplicationModelSnippets/CSharp/App.xaml?highlight=1-7)]
  
 [!code-csharp[HOWTOApplicationModelSnippets#PersistRestoreAppScopePropertiesCODEBEHIND1](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTOApplicationModelSnippets/CSharp/App.xaml.cs?highlight=17-55)]
 [!code-vb[HOWTOApplicationModelSnippets#PersistRestoreAppScopePropertiesCODEBEHIND1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTOApplicationModelSnippets/visualbasic/application.xaml.vb?highlight=14-45)]
