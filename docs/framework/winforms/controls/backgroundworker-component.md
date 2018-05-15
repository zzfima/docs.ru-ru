---
title: Компонент BackgroundWorker
ms.date: 03/30/2017
helpviewer_keywords:
- BackgroundWorker component
- background tasks
- Asynchronous Pattern
- forms [Windows Forms], multithreading
- components [Windows Forms], asynchronous
- forms [Windows Forms], background operations
- threading [Windows Forms], background operations
- background operations
ms.assetid: bef7b0ab-ce57-475a-a2d6-fb8a702a9417
ms.openlocfilehash: 38505876e2f944139622a0d7cf7aaab9c510ef89
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="backgroundworker-component"></a><span data-ttu-id="c306d-102">Компонент BackgroundWorker</span><span class="sxs-lookup"><span data-stu-id="c306d-102">BackgroundWorker Component</span></span>
<span data-ttu-id="c306d-103">`BackgroundWorker` Компонент позволяет формы или элемента управления для асинхронного выполнения операции.</span><span class="sxs-lookup"><span data-stu-id="c306d-103">The `BackgroundWorker` component enables your form or control to run an operation asynchronously.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="c306d-104">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="c306d-104">In This Section</span></span>  
 [<span data-ttu-id="c306d-105">Общие сведения о компоненте BackgroundWorker</span><span class="sxs-lookup"><span data-stu-id="c306d-105">BackgroundWorker Component Overview</span></span>](../../../../docs/framework/winforms/controls/backgroundworker-component-overview.md)  
 <span data-ttu-id="c306d-106">Описывает `BackgroundWorker` компонент, который дает возможность выполнять длительные операции асинхронно (в фоновом режиме»), в потоке, отличном от основного потока пользовательского интерфейса приложения.</span><span class="sxs-lookup"><span data-stu-id="c306d-106">Describes the `BackgroundWorker` component, which gives you the ability to execute time-consuming operations asynchronously ("in the background"), on a thread different from your application's main UI thread.</span></span>  
  
 [<span data-ttu-id="c306d-107">Пример. Фоновое выполнение операции</span><span class="sxs-lookup"><span data-stu-id="c306d-107">Walkthrough: Running an Operation in the Background</span></span>](../../../../docs/framework/winforms/controls/walkthrough-running-an-operation-in-the-background.md)  
 <span data-ttu-id="c306d-108">Демонстрирует использование `BackgroundWorker` компонента в конструкторе для выполнения длительной операции в отдельном потоке.</span><span class="sxs-lookup"><span data-stu-id="c306d-108">Demonstrates how to use the `BackgroundWorker` component in the designer to run a time-consuming operation on a separate thread.</span></span>  
  
 [<span data-ttu-id="c306d-109">Практическое руководство. Фоновое выполнение операции</span><span class="sxs-lookup"><span data-stu-id="c306d-109">How to: Run an Operation in the Background</span></span>](../../../../docs/framework/winforms/controls/how-to-run-an-operation-in-the-background.md)  
 <span data-ttu-id="c306d-110">Демонстрирует использование `BackgroundWorker` компонент для выполнения длительной операции в отдельном потоке.</span><span class="sxs-lookup"><span data-stu-id="c306d-110">Demonstrates how to use the `BackgroundWorker` component to run a time-consuming operation on a separate thread.</span></span>  
  
 [<span data-ttu-id="c306d-111">Пошаговое руководство. Реализация формы, в которой выполняется фоновая операция</span><span class="sxs-lookup"><span data-stu-id="c306d-111">Walkthrough: Implementing a Form That Uses a Background Operation</span></span>](../../../../docs/framework/winforms/controls/walkthrough-implementing-a-form-that-uses-a-background-operation.md)  
 <span data-ttu-id="c306d-112">Создание приложения с помощью конструктора, выполняющего математические вычисления в асинхронном режиме.</span><span class="sxs-lookup"><span data-stu-id="c306d-112">Creates an application using the designer that does mathematical computations asynchronously.</span></span>  
  
 [<span data-ttu-id="c306d-113">Практическое руководство. Реализация формы, в которой выполняется фоновая операция</span><span class="sxs-lookup"><span data-stu-id="c306d-113">How to: Implement a Form That Uses a Background Operation</span></span>](../../../../docs/framework/winforms/controls/how-to-implement-a-form-that-uses-a-background-operation.md)  
 <span data-ttu-id="c306d-114">Создание приложения, выполняющего математические вычисления в асинхронном режиме.</span><span class="sxs-lookup"><span data-stu-id="c306d-114">Creates an application that does mathematical computations asynchronously.</span></span>  
  
 [<span data-ttu-id="c306d-115">Практическое руководство. Фоновая загрузка файла</span><span class="sxs-lookup"><span data-stu-id="c306d-115">How to: Download a File in the Background</span></span>](../../../../docs/framework/winforms/controls/how-to-download-a-file-in-the-background.md)  
 <span data-ttu-id="c306d-116">Демонстрирует использование `BackgroundWorker` компонента для загрузки файла в отдельном потоке.</span><span class="sxs-lookup"><span data-stu-id="c306d-116">Demonstrates how to use the `BackgroundWorker` component to download a file on a separate thread.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="c306d-117">Ссылка</span><span class="sxs-lookup"><span data-stu-id="c306d-117">Reference</span></span>  
 <xref:System.ComponentModel.BackgroundWorker>  
 <span data-ttu-id="c306d-118">Описание класса и всех его членов.</span><span class="sxs-lookup"><span data-stu-id="c306d-118">Describes this class and has links to all its members.</span></span>  
  
 <xref:System.ComponentModel.RunWorkerCompletedEventArgs>  
 <span data-ttu-id="c306d-119">Описывает тип, содержащий данные для <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted> события.</span><span class="sxs-lookup"><span data-stu-id="c306d-119">Describes the type that holds data for the <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted> event.</span></span>  
  
 <xref:System.ComponentModel.ProgressChangedEventArgs>  
 <span data-ttu-id="c306d-120">Описывает тип, содержащий данные для <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> события.</span><span class="sxs-lookup"><span data-stu-id="c306d-120">Describes the type that holds data for the <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> event.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="c306d-121">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="c306d-121">Related Sections</span></span>  
 [<span data-ttu-id="c306d-122">Обзор асинхронной модели, основанной на событиях</span><span class="sxs-lookup"><span data-stu-id="c306d-122">Event-based Asynchronous Pattern Overview</span></span>](../../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md)  
 <span data-ttu-id="c306d-123">Описывает, как асинхронная модель позволяет использовать преимущества многопоточных приложений, скрывая многие сложные проблемы, присущие многопоточности.</span><span class="sxs-lookup"><span data-stu-id="c306d-123">Describes how the asynchronous pattern makes available the advantages of multithreaded applications while hiding many of the complex issues inherent in multithreaded design.</span></span>
