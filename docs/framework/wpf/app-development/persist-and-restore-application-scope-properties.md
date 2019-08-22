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
# <a name="how-to-persist-and-restore-application-scope-properties-across-application-sessions"></a>Практическое руководство. Сохранение и восстановление свойств области определения приложения в сеансах приложения
В этом примере показано, как сохранять свойства области приложения при завершении работы приложения, а также как восстановить свойства области приложения при следующем запуске приложения.  
  
## <a name="example"></a>Пример  
 Приложение сохраняет свойства области приложения в и восстанавливает их из изолированного хранилища. Изолированное хранилище — это защищенная область хранения, которая может безопасно использоваться приложениями без разрешения на доступ к файлам.  Файл *app. XAML* определяет `App_Startup` метод как обработчик для <xref:System.Windows.Application.Startup?displayProperty=nameWithType> события, а `App_Exit` метод — как обработчик для <xref:System.Windows.Application.Exit?displayProperty=nameWithType> события, как показано в выделенных строках первого примера. Во втором примере показана часть файлов *app.XAML.CS* и *app. XAML. vb* , которая выделяет `App_Startup` код для метода, который восстанавливает свойства области приложения, и `App_Exit` метод, сохраняющий область приложения. свойства.

 [!code-xaml[HOWTOApplicationModelSnippets#PersistRestoreAppScopePropertiesXAML1](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTOApplicationModelSnippets/CSharp/App.xaml?highlight=1-7)]
  
 [!code-csharp[HOWTOApplicationModelSnippets#PersistRestoreAppScopePropertiesCODEBEHIND1](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTOApplicationModelSnippets/CSharp/App.xaml.cs?highlight=17-55)]
 [!code-vb[HOWTOApplicationModelSnippets#PersistRestoreAppScopePropertiesCODEBEHIND1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTOApplicationModelSnippets/visualbasic/application.xaml.vb?highlight=14-45)]
