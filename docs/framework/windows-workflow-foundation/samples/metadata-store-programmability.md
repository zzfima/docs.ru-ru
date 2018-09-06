---
title: Программируемость хранилища метаданных
ms.date: 03/30/2017
ms.assetid: 5b613661-f3f9-4e07-8e88-28c9ea2fd8f8
ms.openlocfilehash: 4ea6117686b985a9ea18ce4e5cc4ea2b5c25524c
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/05/2018
ms.locfileid: "43731252"
---
# <a name="metadata-store-programmability"></a><span data-ttu-id="7f196-102">Программируемость хранилища метаданных</span><span class="sxs-lookup"><span data-stu-id="7f196-102">Metadata Store Programmability</span></span>
<span data-ttu-id="7f196-103">Хранилище метаданных является компонентом [!INCLUDE[wfd1](../../../../includes/wfd1-md.md)], позволяющим сопоставлять произвольные метаданные в форме атрибутов CLR с типами во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="7f196-103">The metadata store is a [!INCLUDE[wfd1](../../../../includes/wfd1-md.md)] feature that allows for the association of arbitrary metadata, in the form of CLR attributes, to types at runtime.</span></span> <span data-ttu-id="7f196-104">Это предусматривает слабую связь между компонентами времени выполнения и их аналогами во время разработки, а также возможность изменять компоненты времени разработки, не влияя на время выполнения.</span><span class="sxs-lookup"><span data-stu-id="7f196-104">This allows for a loose coupling between the run-time components and their design-time counterparts, as well as the ability to change the design-time components without affecting the runtime.</span></span> <span data-ttu-id="7f196-105">Образец демонстрирует программирование хранилища метаданных путем применения атрибутов к типам времени выполнения, для которых отсутствует управление их источником.</span><span class="sxs-lookup"><span data-stu-id="7f196-105">The sample shows how to program against the metadata store by applying attributes to a run-time type, the source for which we have no control over.</span></span> <span data-ttu-id="7f196-106">Обычно используется терминология, согласно которой ведущее приложение регистрирует метаданные для набора типов.</span><span class="sxs-lookup"><span data-stu-id="7f196-106">The terminology typically used is that a hosting application registers the metadata for a set of types.</span></span>  
  
 <span data-ttu-id="7f196-107">В выходных данных, вы можете заметить дополнительный непредвиденный атрибут, <!--zz <xref:System.Runtime.InteropServices.GUIDAttribute> --> `System.Runtime.InteropServices.GUIDAttribute`.</span><span class="sxs-lookup"><span data-stu-id="7f196-107">Within the output, you may notice an additional, unexpected attribute, <!--zz <xref:System.Runtime.InteropServices.GUIDAttribute> --> `System.Runtime.InteropServices.GUIDAttribute`.</span></span> <span data-ttu-id="7f196-108">Он добавляется при использовании API-интерфейса метаданных и не влияет на выполнение образца.</span><span class="sxs-lookup"><span data-stu-id="7f196-108">This is added when using the Metadata API and has no impact on the running of the sample.</span></span>  
  
 <span data-ttu-id="7f196-109">В этом образце показаны следующие действия.</span><span class="sxs-lookup"><span data-stu-id="7f196-109">This sample demonstrates:</span></span>  
  
## <a name="demonstrates"></a><span data-ttu-id="7f196-110">Демонстрации</span><span class="sxs-lookup"><span data-stu-id="7f196-110">Demonstrates</span></span>  
  
-   <span data-ttu-id="7f196-111">Внедрение атрибута с использованием API хранилища метаданных.</span><span class="sxs-lookup"><span data-stu-id="7f196-111">Attribute injection using the metadata store API.</span></span>  
  
-   <span data-ttu-id="7f196-112">Использование механизма обратного вызова, чтобы отложить регистрацию метаданных.</span><span class="sxs-lookup"><span data-stu-id="7f196-112">Using a callback mechanism to defer metadata registration.</span></span>  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="7f196-113">Настройка, сборка и выполнение образца</span><span class="sxs-lookup"><span data-stu-id="7f196-113">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="7f196-114">Откройте в среде [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] файл решения ProgrammingMetadataStore.sln.</span><span class="sxs-lookup"><span data-stu-id="7f196-114">Using [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], open the ProgrammingMetadataStore.sln solution file.</span></span>  
  
2.  <span data-ttu-id="7f196-115">Для построения решения нажмите CTRL+SHIFT+B.</span><span class="sxs-lookup"><span data-stu-id="7f196-115">To build the solution, press CTRL+SHIFT+B.</span></span>  
  
3.  <span data-ttu-id="7f196-116">Чтобы запустить решение, нажмите клавишу F5.</span><span class="sxs-lookup"><span data-stu-id="7f196-116">To run the solution, press F5.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="7f196-117">Образцы уже могут быть установлены на компьютере.</span><span class="sxs-lookup"><span data-stu-id="7f196-117">The samples may already be installed on your machine.</span></span> <span data-ttu-id="7f196-118">Перед продолжением проверьте следующий каталог (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="7f196-118">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="7f196-119">Если этот каталог не существует, перейдите к [Windows Communication Foundation (WCF) и образцы Windows Workflow Foundation (WF) для .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) для загрузки всех Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] примеры.</span><span class="sxs-lookup"><span data-stu-id="7f196-119">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="7f196-120">Этот образец расположен в следующем каталоге.</span><span class="sxs-lookup"><span data-stu-id="7f196-120">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\CustomActivities\CustomActivityDesigners\MetadataStore`