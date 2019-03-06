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
ms.openlocfilehash: 2ba3a31d1fe8efde436fd76f88ccfab2853df5ee
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2019
ms.locfileid: "57377141"
---
# <a name="how-to-persist-and-restore-application-scope-properties-across-application-sessions"></a><span data-ttu-id="1a5ae-102">Практическое руководство. Сохранение и восстановление свойств области определения приложения в сеансах приложения</span><span class="sxs-lookup"><span data-stu-id="1a5ae-102">How to: Persist and Restore Application-Scope Properties Across Application Sessions</span></span>
<span data-ttu-id="1a5ae-103">В этом примере показано, как для сохранения свойств области приложения при завершении работы приложения и восстановление свойств области приложения, когда приложение следующего запуска.</span><span class="sxs-lookup"><span data-stu-id="1a5ae-103">This example shows how to persist application-scope properties when an application shuts down, and how to restore application-scope properties when an application is next launch.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1a5ae-104">Пример</span><span class="sxs-lookup"><span data-stu-id="1a5ae-104">Example</span></span>  
 <span data-ttu-id="1a5ae-105">Приложение сохраняет свойства области определения приложения для и восстанавливает их из изолированного хранилища.</span><span class="sxs-lookup"><span data-stu-id="1a5ae-105">The application persists application-scope properties to, and restores them from, isolated storage.</span></span> <span data-ttu-id="1a5ae-106">Изолированное хранилище — это область защищенного хранилища, может безопасно использоваться приложениями без разрешения доступа к файлу.</span><span class="sxs-lookup"><span data-stu-id="1a5ae-106">Isolated storage is a protected storage area that can safely be used by applications without file access permission.</span></span>  <span data-ttu-id="1a5ae-107">*App.xaml* файл определяет `App_Startup` метода как обработчика для <xref:System.Windows.Application.Startup?displayProperty=nameWithType> событий и `App_Exit` метода как обработчика для <xref:System.Windows.Application.Exit?displayProperty=nameWithType> событий, как показано на выделенные строки из первого примера.</span><span class="sxs-lookup"><span data-stu-id="1a5ae-107">The *App.xaml* file defines the `App_Startup` method as the handler for the <xref:System.Windows.Application.Startup?displayProperty=nameWithType> event, and the `App_Exit` method as the handler for the  <xref:System.Windows.Application.Exit?displayProperty=nameWithType> event, as shown in the highlighted lines of the first example.</span></span> <span data-ttu-id="1a5ae-108">Во втором примере показана часть *App.xaml.cs* и *App.xaml.vb* файлы, которые выделяет код `App_Startup` метод, который восстанавливает свойств области приложения и `App_Exit` метод, который сохраняет свойств области приложения.</span><span class="sxs-lookup"><span data-stu-id="1a5ae-108">The second example shows a portion of the *App.xaml.cs* and *App.xaml.vb* files that highlights the code for the `App_Startup` method, which restores application-scope properties, and the `App_Exit` method, which saves application-scope properties.</span></span>
 
  
 [!code-xaml[HOWTOApplicationModelSnippets#PersistRestoreAppScopePropertiesXAML1](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTOApplicationModelSnippets/CSharp/App.xaml?highlight=1-7)]
  
 [!code-csharp[HOWTOApplicationModelSnippets#PersistRestoreAppScopePropertiesCODEBEHIND1](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTOApplicationModelSnippets/CSharp/App.xaml.cs?highlight=17-55)]
 [!code-vb[HOWTOApplicationModelSnippets#PersistRestoreAppScopePropertiesCODEBEHIND1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTOApplicationModelSnippets/visualbasic/application.xaml.vb#persistrestoreappscopepropertiescodebehind1)]
 
