---
title: "Коллекции схемы OLE DB"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6380c36b-658e-4d67-91e8-7131ef4a7c2c
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: e120ea532b6da455e31ce7345b6c4b2be1ec975f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="ole-db-schema-collections"></a><span data-ttu-id="9b705-102">Коллекции схемы OLE DB</span><span class="sxs-lookup"><span data-stu-id="9b705-102">OLE DB Schema Collections</span></span>
<span data-ttu-id="9b705-103">В данном разделе рассматривается поддержка коллекций схем для поставщиков OLE DB для Microsoft SQL Server, Oracle и Microsoft Jet.</span><span class="sxs-lookup"><span data-stu-id="9b705-103">This section discusses schema collection support for the OLE DB providers for Microsoft SQL Server, Oracle, and Microsoft Jet.</span></span>  
  
## <a name="microsoft-sql-server-ole-db-provider"></a><span data-ttu-id="9b705-104">Поставщик OLE DB для Microsoft SQL Server</span><span class="sxs-lookup"><span data-stu-id="9b705-104">Microsoft SQL Server OLE DB Provider</span></span>  
 <span data-ttu-id="9b705-105">Драйвер Microsoft SQL Server OLE DB поддерживает следующие специальные коллекции схем в дополнение к общим коллекциям схем:</span><span class="sxs-lookup"><span data-stu-id="9b705-105">The Microsoft SQL Server OLE DB Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
-   <span data-ttu-id="9b705-106">Таблицы</span><span class="sxs-lookup"><span data-stu-id="9b705-106">Tables</span></span>  
  
-   <span data-ttu-id="9b705-107">Столбцы</span><span class="sxs-lookup"><span data-stu-id="9b705-107">Columns</span></span>  
  
-   <span data-ttu-id="9b705-108">Процедуры</span><span class="sxs-lookup"><span data-stu-id="9b705-108">Procedures</span></span>  
  
-   <span data-ttu-id="9b705-109">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="9b705-109">ProcedureParameters</span></span>  
  
-   <span data-ttu-id="9b705-110">Catalog</span><span class="sxs-lookup"><span data-stu-id="9b705-110">Catalog</span></span>  
  
-   <span data-ttu-id="9b705-111">Indexes</span><span class="sxs-lookup"><span data-stu-id="9b705-111">Indexes</span></span>  
  
### <a name="tables"></a><span data-ttu-id="9b705-112">Таблицы</span><span class="sxs-lookup"><span data-stu-id="9b705-112">Tables</span></span>  
  
|<span data-ttu-id="9b705-113">ColumnName</span><span class="sxs-lookup"><span data-stu-id="9b705-113">ColumnName</span></span>|<span data-ttu-id="9b705-114">DataType</span><span class="sxs-lookup"><span data-stu-id="9b705-114">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="9b705-115">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="9b705-115">TABLE_CATALOG</span></span>|<span data-ttu-id="9b705-116">Строковое</span><span class="sxs-lookup"><span data-stu-id="9b705-116">String</span></span>|  
|<span data-ttu-id="9b705-117">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="9b705-117">TABLE_SCHEMA</span></span>|<span data-ttu-id="9b705-118">Строковое</span><span class="sxs-lookup"><span data-stu-id="9b705-118">String</span></span>|  
|<span data-ttu-id="9b705-119">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="9b705-119">TABLE_NAME</span></span>|<span data-ttu-id="9b705-120">Строковое</span><span class="sxs-lookup"><span data-stu-id="9b705-120">String</span></span>|  
|<span data-ttu-id="9b705-121">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="9b705-121">TABLE_TYPE</span></span>|<span data-ttu-id="9b705-122">Строковое</span><span class="sxs-lookup"><span data-stu-id="9b705-122">String</span></span>|  
|<span data-ttu-id="9b705-123">TABLE_GUID</span><span class="sxs-lookup"><span data-stu-id="9b705-123">TABLE_GUID</span></span>|<span data-ttu-id="9b705-124">Guid</span><span class="sxs-lookup"><span data-stu-id="9b705-124">Guid</span></span>|  
|<span data-ttu-id="9b705-125">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="9b705-125">DESCRIPTION</span></span>|<span data-ttu-id="9b705-126">Строковое</span><span class="sxs-lookup"><span data-stu-id="9b705-126">String</span></span>|  
|<span data-ttu-id="9b705-127">TABLE_PROPID</span><span class="sxs-lookup"><span data-stu-id="9b705-127">TABLE_PROPID</span></span>|<span data-ttu-id="9b705-128">Int64</span><span class="sxs-lookup"><span data-stu-id="9b705-128">Int64</span></span>|  
|<span data-ttu-id="9b705-129">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="9b705-129">DATE_CREATED</span></span>|<span data-ttu-id="9b705-130">DateTime</span><span class="sxs-lookup"><span data-stu-id="9b705-130">DateTime</span></span>|  
|<span data-ttu-id="9b705-131">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="9b705-131">DATE_MODIFIED</span></span>|<span data-ttu-id="9b705-132">DateTime</span><span class="sxs-lookup"><span data-stu-id="9b705-132">DateTime</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="9b705-133">Столбцы</span><span class="sxs-lookup"><span data-stu-id="9b705-133">Columns</span></span>  
  
|<span data-ttu-id="9b705-134">ColumnName</span><span class="sxs-lookup"><span data-stu-id="9b705-134">ColumnName</span></span>|<span data-ttu-id="9b705-135">DataType</span><span class="sxs-lookup"><span data-stu-id="9b705-135">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="9b705-136">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="9b705-136">TABLE_CATALOG</span></span>|<span data-ttu-id="9b705-137">Строковое</span><span class="sxs-lookup"><span data-stu-id="9b705-137">String</span></span>|  
|<span data-ttu-id="9b705-138">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="9b705-138">TABLE_SCHEMA</span></span>|<span data-ttu-id="9b705-139">Строковое</span><span class="sxs-lookup"><span data-stu-id="9b705-139">String</span></span>|  
|<span data-ttu-id="9b705-140">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="9b705-140">TABLE_NAME</span></span>|<span data-ttu-id="9b705-141">Строковое</span><span class="sxs-lookup"><span data-stu-id="9b705-141">String</span></span>|  
|<span data-ttu-id="9b705-142">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="9b705-142">COLUMN_NAME</span></span>|<span data-ttu-id="9b705-143">Строковое</span><span class="sxs-lookup"><span data-stu-id="9b705-143">String</span></span>|  
|<span data-ttu-id="9b705-144">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="9b705-144">COLUMN_GUID</span></span>|<span data-ttu-id="9b705-145">Guid</span><span class="sxs-lookup"><span data-stu-id="9b705-145">Guid</span></span>|  
|<span data-ttu-id="9b705-146">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="9b705-146">COLUMN_PROPID</span></span>|<span data-ttu-id="9b705-147">Int64</span><span class="sxs-lookup"><span data-stu-id="9b705-147">Int64</span></span>|  
|<span data-ttu-id="9b705-148">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="9b705-148">ORDINAL_POSITION</span></span>|<span data-ttu-id="9b705-149">Int64</span><span class="sxs-lookup"><span data-stu-id="9b705-149">Int64</span></span>|  
|<span data-ttu-id="9b705-150">COLUMN_HASDEFAULT</span><span class="sxs-lookup"><span data-stu-id="9b705-150">COLUMN_HASDEFAULT</span></span>|<span data-ttu-id="9b705-151">Boolean</span><span class="sxs-lookup"><span data-stu-id="9b705-151">Boolean</span></span>|  
|<span data-ttu-id="9b705-152">COLUMN_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="9b705-152">COLUMN_DEFAULT</span></span>|<span data-ttu-id="9b705-153">Строковое</span><span class="sxs-lookup"><span data-stu-id="9b705-153">String</span></span>|  
|<span data-ttu-id="9b705-154">COLUMN_FLAGS</span><span class="sxs-lookup"><span data-stu-id="9b705-154">COLUMN_FLAGS</span></span>|<span data-ttu-id="9b705-155">Int64</span><span class="sxs-lookup"><span data-stu-id="9b705-155">Int64</span></span>|  
|<span data-ttu-id="9b705-156">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="9b705-156">IS_NULLABLE</span></span>|<span data-ttu-id="9b705-157">Boolean</span><span class="sxs-lookup"><span data-stu-id="9b705-157">Boolean</span></span>|  
|<span data-ttu-id="9b705-158">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="9b705-158">DATA_TYPE</span></span>|<span data-ttu-id="9b705-159">Int32</span><span class="sxs-lookup"><span data-stu-id="9b705-159">Int32</span></span>|  
|<span data-ttu-id="9b705-160">TYPE_GUID</span><span class="sxs-lookup"><span data-stu-id="9b705-160">TYPE_GUID</span></span>|<span data-ttu-id="9b705-161">Guid</span><span class="sxs-lookup"><span data-stu-id="9b705-161">Guid</span></span>|  
|<span data-ttu-id="9b705-162">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="9b705-162">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="9b705-163">Int64</span><span class="sxs-lookup"><span data-stu-id="9b705-163">Int64</span></span>|  
|<span data-ttu-id="9b705-164">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="9b705-164">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="9b705-165">Int64</span><span class="sxs-lookup"><span data-stu-id="9b705-165">Int64</span></span>|  
|<span data-ttu-id="9b705-166">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="9b705-166">NUMERIC_PRECISION</span></span>|<span data-ttu-id="9b705-167">Int32</span><span class="sxs-lookup"><span data-stu-id="9b705-167">Int32</span></span>|  
|<span data-ttu-id="9b705-168">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="9b705-168">NUMERIC_SCALE</span></span>|<span data-ttu-id="9b705-169">Int16</span><span class="sxs-lookup"><span data-stu-id="9b705-169">Int16</span></span>|  
|<span data-ttu-id="9b705-170">DATETIME_PRECISION</span><span class="sxs-lookup"><span data-stu-id="9b705-170">DATETIME_PRECISION</span></span>|<span data-ttu-id="9b705-171">Int64</span><span class="sxs-lookup"><span data-stu-id="9b705-171">Int64</span></span>|  
|<span data-ttu-id="9b705-172">CHARACTER_SET_CATALOG</span><span class="sxs-lookup"><span data-stu-id="9b705-172">CHARACTER_SET_CATALOG</span></span>|<span data-ttu-id="9b705-173">Строковое</span><span class="sxs-lookup"><span data-stu-id="9b705-173">String</span></span>|  
|<span data-ttu-id="9b705-174">CHARACTER_SET_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="9b705-174">CHARACTER_SET_SCHEMA</span></span>|<span data-ttu-id="9b705-175">Строковое</span><span class="sxs-lookup"><span data-stu-id="9b705-175">String</span></span>|  
|<span data-ttu-id="9b705-176">CHARACTER_SET_NAME</span><span class="sxs-lookup"><span data-stu-id="9b705-176">CHARACTER_SET_NAME</span></span>|<span data-ttu-id="9b705-177">Строковое</span><span class="sxs-lookup"><span data-stu-id="9b705-177">String</span></span>|  
|<span data-ttu-id="9b705-178">COLLATION_CATALOG</span><span class="sxs-lookup"><span data-stu-id="9b705-178">COLLATION_CATALOG</span></span>|<span data-ttu-id="9b705-179">Строковое</span><span class="sxs-lookup"><span data-stu-id="9b705-179">String</span></span>|  
|<span data-ttu-id="9b705-180">COLLATION_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="9b705-180">COLLATION_SCHEMA</span></span>|<span data-ttu-id="9b705-181">Строковое</span><span class="sxs-lookup"><span data-stu-id="9b705-181">String</span></span>|  
|<span data-ttu-id="9b705-182">COLLATION_NAME</span><span class="sxs-lookup"><span data-stu-id="9b705-182">COLLATION_NAME</span></span>|<span data-ttu-id="9b705-183">Строковое</span><span class="sxs-lookup"><span data-stu-id="9b705-183">String</span></span>|  
|<span data-ttu-id="9b705-184">DOMAIN_CATALOG</span><span class="sxs-lookup"><span data-stu-id="9b705-184">DOMAIN_CATALOG</span></span>|<span data-ttu-id="9b705-185">Строковое</span><span class="sxs-lookup"><span data-stu-id="9b705-185">String</span></span>|  
|<span data-ttu-id="9b705-186">DOMAIN_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="9b705-186">DOMAIN_SCHEMA</span></span>|<span data-ttu-id="9b705-187">Строковое</span><span class="sxs-lookup"><span data-stu-id="9b705-187">String</span></span>|  
|<span data-ttu-id="9b705-188">DOMAIN_NAME</span><span class="sxs-lookup"><span data-stu-id="9b705-188">DOMAIN_NAME</span></span>|<span data-ttu-id="9b705-189">Строковое</span><span class="sxs-lookup"><span data-stu-id="9b705-189">String</span></span>|  
|<span data-ttu-id="9b705-190">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="9b705-190">DESCRIPTION</span></span>|<span data-ttu-id="9b705-191">Строковое</span><span class="sxs-lookup"><span data-stu-id="9b705-191">String</span></span>|  
|<span data-ttu-id="9b705-192">COLUMN_LCID</span><span class="sxs-lookup"><span data-stu-id="9b705-192">COLUMN_LCID</span></span>|<span data-ttu-id="9b705-193">Int32</span><span class="sxs-lookup"><span data-stu-id="9b705-193">Int32</span></span>|  
|<span data-ttu-id="9b705-194">COLUMN_COMPFLAGS</span><span class="sxs-lookup"><span data-stu-id="9b705-194">COLUMN_COMPFLAGS</span></span>|<span data-ttu-id="9b705-195">Int32</span><span class="sxs-lookup"><span data-stu-id="9b705-195">Int32</span></span>|  
|<span data-ttu-id="9b705-196">COLUMN_SORTID</span><span class="sxs-lookup"><span data-stu-id="9b705-196">COLUMN_SORTID</span></span>|<span data-ttu-id="9b705-197">Int32</span><span class="sxs-lookup"><span data-stu-id="9b705-197">Int32</span></span>|  
|<span data-ttu-id="9b705-198">COLUMN_TDSCOLLATION</span><span class="sxs-lookup"><span data-stu-id="9b705-198">COLUMN_TDSCOLLATION</span></span>|<span data-ttu-id="9b705-199">Byte[]</span><span class="sxs-lookup"><span data-stu-id="9b705-199">Byte[]</span></span>|  
|<span data-ttu-id="9b705-200">IS_COMPUTED</span><span class="sxs-lookup"><span data-stu-id="9b705-200">IS_COMPUTED</span></span>|<span data-ttu-id="9b705-201">Boolean</span><span class="sxs-lookup"><span data-stu-id="9b705-201">Boolean</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="9b705-202">Процедуры</span><span class="sxs-lookup"><span data-stu-id="9b705-202">Procedures</span></span>  
  
|<span data-ttu-id="9b705-203">ColumnName</span><span class="sxs-lookup"><span data-stu-id="9b705-203">ColumnName</span></span>|<span data-ttu-id="9b705-204">DataType</span><span class="sxs-lookup"><span data-stu-id="9b705-204">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="9b705-205">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="9b705-205">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="9b705-206">Строковое</span><span class="sxs-lookup"><span data-stu-id="9b705-206">String</span></span>|  
|<span data-ttu-id="9b705-207">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="9b705-207">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="9b705-208">Строковое</span><span class="sxs-lookup"><span data-stu-id="9b705-208">String</span></span>|  
|<span data-ttu-id="9b705-209">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="9b705-209">PROCEDURE_NAME</span></span>|<span data-ttu-id="9b705-210">Строковое</span><span class="sxs-lookup"><span data-stu-id="9b705-210">String</span></span>|  
|<span data-ttu-id="9b705-211">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="9b705-211">PROCEDURE_TYPE</span></span>|<span data-ttu-id="9b705-212">Int16</span><span class="sxs-lookup"><span data-stu-id="9b705-212">Int16</span></span>|  
|<span data-ttu-id="9b705-213">PROCEDURE_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="9b705-213">PROCEDURE_DEFINITION</span></span>|<span data-ttu-id="9b705-214">Строковое</span><span class="sxs-lookup"><span data-stu-id="9b705-214">String</span></span>|  
|<span data-ttu-id="9b705-215">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="9b705-215">DESCRIPTION</span></span>|<span data-ttu-id="9b705-216">Строковое</span><span class="sxs-lookup"><span data-stu-id="9b705-216">String</span></span>|  
|<span data-ttu-id="9b705-217">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="9b705-217">DATE_CREATED</span></span>|<span data-ttu-id="9b705-218">DateTime</span><span class="sxs-lookup"><span data-stu-id="9b705-218">DateTime</span></span>|  
|<span data-ttu-id="9b705-219">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="9b705-219">DATE_MODIFIED</span></span>|<span data-ttu-id="9b705-220">DateTime</span><span class="sxs-lookup"><span data-stu-id="9b705-220">DateTime</span></span>|  
  
### <a name="procedureparameters"></a><span data-ttu-id="9b705-221">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="9b705-221">ProcedureParameters</span></span>  
  
|<span data-ttu-id="9b705-222">ColumnName</span><span class="sxs-lookup"><span data-stu-id="9b705-222">ColumnName</span></span>|<span data-ttu-id="9b705-223">DataType</span><span class="sxs-lookup"><span data-stu-id="9b705-223">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="9b705-224">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="9b705-224">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="9b705-225">Строковое</span><span class="sxs-lookup"><span data-stu-id="9b705-225">String</span></span>|  
|<span data-ttu-id="9b705-226">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="9b705-226">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="9b705-227">Строковое</span><span class="sxs-lookup"><span data-stu-id="9b705-227">String</span></span>|  
|<span data-ttu-id="9b705-228">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="9b705-228">PROCEDURE_NAME</span></span>|<span data-ttu-id="9b705-229">Строковое</span><span class="sxs-lookup"><span data-stu-id="9b705-229">String</span></span>|  
|<span data-ttu-id="9b705-230">PARAMETER_NAME</span><span class="sxs-lookup"><span data-stu-id="9b705-230">PARAMETER_NAME</span></span>|<span data-ttu-id="9b705-231">Строковое</span><span class="sxs-lookup"><span data-stu-id="9b705-231">String</span></span>|  
|<span data-ttu-id="9b705-232">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="9b705-232">ORDINAL_POSITION</span></span>|<span data-ttu-id="9b705-233">Int32</span><span class="sxs-lookup"><span data-stu-id="9b705-233">Int32</span></span>|  
|<span data-ttu-id="9b705-234">PARAMETER_TYPE</span><span class="sxs-lookup"><span data-stu-id="9b705-234">PARAMETER_TYPE</span></span>|<span data-ttu-id="9b705-235">Int32</span><span class="sxs-lookup"><span data-stu-id="9b705-235">Int32</span></span>|  
|<span data-ttu-id="9b705-236">PARAMETER_HASDEFAULT</span><span class="sxs-lookup"><span data-stu-id="9b705-236">PARAMETER_HASDEFAULT</span></span>|<span data-ttu-id="9b705-237">Boolean</span><span class="sxs-lookup"><span data-stu-id="9b705-237">Boolean</span></span>|  
|<span data-ttu-id="9b705-238">PARAMETER_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="9b705-238">PARAMETER_DEFAULT</span></span>|<span data-ttu-id="9b705-239">Строковое</span><span class="sxs-lookup"><span data-stu-id="9b705-239">String</span></span>|  
|<span data-ttu-id="9b705-240">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="9b705-240">IS_NULLABLE</span></span>|<span data-ttu-id="9b705-241">Boolean</span><span class="sxs-lookup"><span data-stu-id="9b705-241">Boolean</span></span>|  
|<span data-ttu-id="9b705-242">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="9b705-242">DATA_TYPE</span></span>|<span data-ttu-id="9b705-243">Int32</span><span class="sxs-lookup"><span data-stu-id="9b705-243">Int32</span></span>|  
|<span data-ttu-id="9b705-244">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="9b705-244">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="9b705-245">Int64</span><span class="sxs-lookup"><span data-stu-id="9b705-245">Int64</span></span>|  
|<span data-ttu-id="9b705-246">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="9b705-246">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="9b705-247">Int64</span><span class="sxs-lookup"><span data-stu-id="9b705-247">Int64</span></span>|  
|<span data-ttu-id="9b705-248">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="9b705-248">NUMERIC_PRECISION</span></span>|<span data-ttu-id="9b705-249">Int32</span><span class="sxs-lookup"><span data-stu-id="9b705-249">Int32</span></span>|  
|<span data-ttu-id="9b705-250">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="9b705-250">NUMERIC_SCALE</span></span>|<span data-ttu-id="9b705-251">Int16</span><span class="sxs-lookup"><span data-stu-id="9b705-251">Int16</span></span>|  
|<span data-ttu-id="9b705-252">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="9b705-252">DESCRIPTION</span></span>|<span data-ttu-id="9b705-253">Строковое</span><span class="sxs-lookup"><span data-stu-id="9b705-253">String</span></span>|  
|<span data-ttu-id="9b705-254">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="9b705-254">TYPE_NAME</span></span>|<span data-ttu-id="9b705-255">Строковое</span><span class="sxs-lookup"><span data-stu-id="9b705-255">String</span></span>|  
|<span data-ttu-id="9b705-256">LOCAL_TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="9b705-256">LOCAL_TYPE_NAME</span></span>|<span data-ttu-id="9b705-257">Строковое</span><span class="sxs-lookup"><span data-stu-id="9b705-257">String</span></span>|  
  
### <a name="catalog"></a><span data-ttu-id="9b705-258">Catalog</span><span class="sxs-lookup"><span data-stu-id="9b705-258">Catalog</span></span>  
  
|<span data-ttu-id="9b705-259">ColumnName</span><span class="sxs-lookup"><span data-stu-id="9b705-259">ColumnName</span></span>|<span data-ttu-id="9b705-260">DataType</span><span class="sxs-lookup"><span data-stu-id="9b705-260">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="9b705-261">CATALOG_NAME</span><span class="sxs-lookup"><span data-stu-id="9b705-261">CATALOG_NAME</span></span>|<span data-ttu-id="9b705-262">Строковое</span><span class="sxs-lookup"><span data-stu-id="9b705-262">String</span></span>|  
|<span data-ttu-id="9b705-263">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="9b705-263">DESCRIPTION</span></span>|<span data-ttu-id="9b705-264">Строковое</span><span class="sxs-lookup"><span data-stu-id="9b705-264">String</span></span>|  
  
### <a name="indexes"></a><span data-ttu-id="9b705-265">Indexes</span><span class="sxs-lookup"><span data-stu-id="9b705-265">Indexes</span></span>  
  
|<span data-ttu-id="9b705-266">ColumnName</span><span class="sxs-lookup"><span data-stu-id="9b705-266">ColumnName</span></span>|<span data-ttu-id="9b705-267">DataType</span><span class="sxs-lookup"><span data-stu-id="9b705-267">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="9b705-268">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="9b705-268">TABLE_CATALOG</span></span>|<span data-ttu-id="9b705-269">Строковое</span><span class="sxs-lookup"><span data-stu-id="9b705-269">String</span></span>|  
|<span data-ttu-id="9b705-270">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="9b705-270">TABLE_SCHEMA</span></span>|<span data-ttu-id="9b705-271">Строковое</span><span class="sxs-lookup"><span data-stu-id="9b705-271">String</span></span>|  
|<span data-ttu-id="9b705-272">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="9b705-272">TABLE_NAME</span></span>|<span data-ttu-id="9b705-273">Строковое</span><span class="sxs-lookup"><span data-stu-id="9b705-273">String</span></span>|  
|<span data-ttu-id="9b705-274">INDEX_CATALOG</span><span class="sxs-lookup"><span data-stu-id="9b705-274">INDEX_CATALOG</span></span>|<span data-ttu-id="9b705-275">Строковое</span><span class="sxs-lookup"><span data-stu-id="9b705-275">String</span></span>|  
|<span data-ttu-id="9b705-276">INDEX_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="9b705-276">INDEX_SCHEMA</span></span>|<span data-ttu-id="9b705-277">Строковое</span><span class="sxs-lookup"><span data-stu-id="9b705-277">String</span></span>|  
|<span data-ttu-id="9b705-278">INDEX_NAME</span><span class="sxs-lookup"><span data-stu-id="9b705-278">INDEX_NAME</span></span>|<span data-ttu-id="9b705-279">Строковое</span><span class="sxs-lookup"><span data-stu-id="9b705-279">String</span></span>|  
|<span data-ttu-id="9b705-280">PRIMARY_KEY</span><span class="sxs-lookup"><span data-stu-id="9b705-280">PRIMARY_KEY</span></span>|<span data-ttu-id="9b705-281">Boolean</span><span class="sxs-lookup"><span data-stu-id="9b705-281">Boolean</span></span>|  
|<span data-ttu-id="9b705-282">UNIQUE</span><span class="sxs-lookup"><span data-stu-id="9b705-282">UNIQUE</span></span>|<span data-ttu-id="9b705-283">Boolean</span><span class="sxs-lookup"><span data-stu-id="9b705-283">Boolean</span></span>|  
|<span data-ttu-id="9b705-284">CLUSTERED</span><span class="sxs-lookup"><span data-stu-id="9b705-284">CLUSTERED</span></span>|<span data-ttu-id="9b705-285">Boolean</span><span class="sxs-lookup"><span data-stu-id="9b705-285">Boolean</span></span>|  
|<span data-ttu-id="9b705-286">TYPE</span><span class="sxs-lookup"><span data-stu-id="9b705-286">TYPE</span></span>|<span data-ttu-id="9b705-287">Int32</span><span class="sxs-lookup"><span data-stu-id="9b705-287">Int32</span></span>|  
|<span data-ttu-id="9b705-288">FILL_FACTOR</span><span class="sxs-lookup"><span data-stu-id="9b705-288">FILL_FACTOR</span></span>|<span data-ttu-id="9b705-289">Int32</span><span class="sxs-lookup"><span data-stu-id="9b705-289">Int32</span></span>|  
|<span data-ttu-id="9b705-290">INITIAL_SIZE</span><span class="sxs-lookup"><span data-stu-id="9b705-290">INITIAL_SIZE</span></span>|<span data-ttu-id="9b705-291">Int32</span><span class="sxs-lookup"><span data-stu-id="9b705-291">Int32</span></span>|  
|<span data-ttu-id="9b705-292">NULLS</span><span class="sxs-lookup"><span data-stu-id="9b705-292">NULLS</span></span>|<span data-ttu-id="9b705-293">Int32</span><span class="sxs-lookup"><span data-stu-id="9b705-293">Int32</span></span>|  
|<span data-ttu-id="9b705-294">SORT_BOOKMARKS</span><span class="sxs-lookup"><span data-stu-id="9b705-294">SORT_BOOKMARKS</span></span>|<span data-ttu-id="9b705-295">Boolean</span><span class="sxs-lookup"><span data-stu-id="9b705-295">Boolean</span></span>|  
|<span data-ttu-id="9b705-296">AUTO_UPDATE</span><span class="sxs-lookup"><span data-stu-id="9b705-296">AUTO_UPDATE</span></span>|<span data-ttu-id="9b705-297">Boolean</span><span class="sxs-lookup"><span data-stu-id="9b705-297">Boolean</span></span>|  
|<span data-ttu-id="9b705-298">NULL_COLLATION</span><span class="sxs-lookup"><span data-stu-id="9b705-298">NULL_COLLATION</span></span>|<span data-ttu-id="9b705-299">Int32</span><span class="sxs-lookup"><span data-stu-id="9b705-299">Int32</span></span>|  
|<span data-ttu-id="9b705-300">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="9b705-300">ORDINAL_POSITION</span></span>|<span data-ttu-id="9b705-301">Int64</span><span class="sxs-lookup"><span data-stu-id="9b705-301">Int64</span></span>|  
|<span data-ttu-id="9b705-302">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="9b705-302">COLUMN_NAME</span></span>|<span data-ttu-id="9b705-303">Строковое</span><span class="sxs-lookup"><span data-stu-id="9b705-303">String</span></span>|  
|<span data-ttu-id="9b705-304">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="9b705-304">COLUMN_GUID</span></span>|<span data-ttu-id="9b705-305">Guid</span><span class="sxs-lookup"><span data-stu-id="9b705-305">Guid</span></span>|  
|<span data-ttu-id="9b705-306">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="9b705-306">COLUMN_PROPID</span></span>|<span data-ttu-id="9b705-307">Int64</span><span class="sxs-lookup"><span data-stu-id="9b705-307">Int64</span></span>|  
|<span data-ttu-id="9b705-308">COLLATION</span><span class="sxs-lookup"><span data-stu-id="9b705-308">COLLATION</span></span>|<span data-ttu-id="9b705-309">Int16</span><span class="sxs-lookup"><span data-stu-id="9b705-309">Int16</span></span>|  
|<span data-ttu-id="9b705-310">CARDINALITY</span><span class="sxs-lookup"><span data-stu-id="9b705-310">CARDINALITY</span></span>|<span data-ttu-id="9b705-311">Десятичное число</span><span class="sxs-lookup"><span data-stu-id="9b705-311">Decimal</span></span>|  
|<span data-ttu-id="9b705-312">PAGES</span><span class="sxs-lookup"><span data-stu-id="9b705-312">PAGES</span></span>|<span data-ttu-id="9b705-313">Int32</span><span class="sxs-lookup"><span data-stu-id="9b705-313">Int32</span></span>|  
|<span data-ttu-id="9b705-314">FILTER_CONDITION</span><span class="sxs-lookup"><span data-stu-id="9b705-314">FILTER_CONDITION</span></span>|<span data-ttu-id="9b705-315">Строковое</span><span class="sxs-lookup"><span data-stu-id="9b705-315">String</span></span>|  
|<span data-ttu-id="9b705-316">INTEGRATED</span><span class="sxs-lookup"><span data-stu-id="9b705-316">INTEGRATED</span></span>|<span data-ttu-id="9b705-317">Boolean</span><span class="sxs-lookup"><span data-stu-id="9b705-317">Boolean</span></span>|  
  
## <a name="microsoft-oracle-ole-db-provider"></a><span data-ttu-id="9b705-318">Поставщик Microsoft OLE DB для Oracle</span><span class="sxs-lookup"><span data-stu-id="9b705-318">Microsoft Oracle OLE DB Provider</span></span>  
 <span data-ttu-id="9b705-319">Драйвер OLE DB для Oracle (Майкрософт) поддерживает следующие специальные коллекции схем в дополнение к общим коллекциям.</span><span class="sxs-lookup"><span data-stu-id="9b705-319">The Microsoft Oracle OLE DB Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
-   <span data-ttu-id="9b705-320">Таблицы</span><span class="sxs-lookup"><span data-stu-id="9b705-320">Tables</span></span>  
  
-   <span data-ttu-id="9b705-321">Столбцы</span><span class="sxs-lookup"><span data-stu-id="9b705-321">Columns</span></span>  
  
-   <span data-ttu-id="9b705-322">Процедуры</span><span class="sxs-lookup"><span data-stu-id="9b705-322">Procedures</span></span>  
  
-   <span data-ttu-id="9b705-323">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="9b705-323">ProcedureColumns</span></span>  
  
-   <span data-ttu-id="9b705-324">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="9b705-324">ProcedureParameters</span></span>  
  
-   <span data-ttu-id="9b705-325">Представления</span><span class="sxs-lookup"><span data-stu-id="9b705-325">Views</span></span>  
  
-   <span data-ttu-id="9b705-326">Indexes</span><span class="sxs-lookup"><span data-stu-id="9b705-326">Indexes</span></span>  
  
### <a name="tables"></a><span data-ttu-id="9b705-327">Таблицы</span><span class="sxs-lookup"><span data-stu-id="9b705-327">Tables</span></span>  
  
|<span data-ttu-id="9b705-328">ColumnName</span><span class="sxs-lookup"><span data-stu-id="9b705-328">ColumnName</span></span>|<span data-ttu-id="9b705-329">DataType</span><span class="sxs-lookup"><span data-stu-id="9b705-329">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="9b705-330">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="9b705-330">TABLE_CATALOG</span></span>|<span data-ttu-id="9b705-331">Строковое</span><span class="sxs-lookup"><span data-stu-id="9b705-331">String</span></span>|  
|<span data-ttu-id="9b705-332">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="9b705-332">TABLE_SCHEMA</span></span>|<span data-ttu-id="9b705-333">Строковое</span><span class="sxs-lookup"><span data-stu-id="9b705-333">String</span></span>|  
|<span data-ttu-id="9b705-334">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="9b705-334">TABLE_NAME</span></span>|<span data-ttu-id="9b705-335">Строковое</span><span class="sxs-lookup"><span data-stu-id="9b705-335">String</span></span>|  
|<span data-ttu-id="9b705-336">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="9b705-336">TABLE_TYPE</span></span>|<span data-ttu-id="9b705-337">Строковое</span><span class="sxs-lookup"><span data-stu-id="9b705-337">String</span></span>|  
|<span data-ttu-id="9b705-338">TABLE_GUID</span><span class="sxs-lookup"><span data-stu-id="9b705-338">TABLE_GUID</span></span>|<span data-ttu-id="9b705-339">Guid</span><span class="sxs-lookup"><span data-stu-id="9b705-339">Guid</span></span>|  
|<span data-ttu-id="9b705-340">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="9b705-340">DESCRIPTION</span></span>|<span data-ttu-id="9b705-341">Строковое</span><span class="sxs-lookup"><span data-stu-id="9b705-341">String</span></span>|  
|<span data-ttu-id="9b705-342">TABLE_PROPID</span><span class="sxs-lookup"><span data-stu-id="9b705-342">TABLE_PROPID</span></span>|<span data-ttu-id="9b705-343">Int64</span><span class="sxs-lookup"><span data-stu-id="9b705-343">Int64</span></span>|  
|<span data-ttu-id="9b705-344">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="9b705-344">DATE_CREATED</span></span>|<span data-ttu-id="9b705-345">DateTime</span><span class="sxs-lookup"><span data-stu-id="9b705-345">DateTime</span></span>|  
|<span data-ttu-id="9b705-346">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="9b705-346">DATE_MODIFIED</span></span>|<span data-ttu-id="9b705-347">DateTime</span><span class="sxs-lookup"><span data-stu-id="9b705-347">DateTime</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="9b705-348">Столбцы</span><span class="sxs-lookup"><span data-stu-id="9b705-348">Columns</span></span>  
  
|<span data-ttu-id="9b705-349">ColumnName</span><span class="sxs-lookup"><span data-stu-id="9b705-349">ColumnName</span></span>|<span data-ttu-id="9b705-350">DataType</span><span class="sxs-lookup"><span data-stu-id="9b705-350">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="9b705-351">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="9b705-351">TABLE_CATALOG</span></span>|<span data-ttu-id="9b705-352">Строковое</span><span class="sxs-lookup"><span data-stu-id="9b705-352">String</span></span>|  
|<span data-ttu-id="9b705-353">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="9b705-353">TABLE_SCHEMA</span></span>|<span data-ttu-id="9b705-354">Строковое</span><span class="sxs-lookup"><span data-stu-id="9b705-354">String</span></span>|  
|<span data-ttu-id="9b705-355">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="9b705-355">TABLE_NAME</span></span>|<span data-ttu-id="9b705-356">Строковое</span><span class="sxs-lookup"><span data-stu-id="9b705-356">String</span></span>|  
|<span data-ttu-id="9b705-357">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="9b705-357">COLUMN_NAME</span></span>|<span data-ttu-id="9b705-358">Строковое</span><span class="sxs-lookup"><span data-stu-id="9b705-358">String</span></span>|  
|<span data-ttu-id="9b705-359">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="9b705-359">COLUMN_GUID</span></span>|<span data-ttu-id="9b705-360">Guid</span><span class="sxs-lookup"><span data-stu-id="9b705-360">Guid</span></span>|  
|<span data-ttu-id="9b705-361">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="9b705-361">COLUMN_PROPID</span></span>|<span data-ttu-id="9b705-362">Int64</span><span class="sxs-lookup"><span data-stu-id="9b705-362">Int64</span></span>|  
|<span data-ttu-id="9b705-363">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="9b705-363">ORDINAL_POSITION</span></span>|<span data-ttu-id="9b705-364">Int64</span><span class="sxs-lookup"><span data-stu-id="9b705-364">Int64</span></span>|  
|<span data-ttu-id="9b705-365">COLUMN_HASDEFAULT</span><span class="sxs-lookup"><span data-stu-id="9b705-365">COLUMN_HASDEFAULT</span></span>|<span data-ttu-id="9b705-366">Boolean</span><span class="sxs-lookup"><span data-stu-id="9b705-366">Boolean</span></span>|  
|<span data-ttu-id="9b705-367">COLUMN_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="9b705-367">COLUMN_DEFAULT</span></span>|<span data-ttu-id="9b705-368">Строковое</span><span class="sxs-lookup"><span data-stu-id="9b705-368">String</span></span>|  
|<span data-ttu-id="9b705-369">COLUMN_FLAGS</span><span class="sxs-lookup"><span data-stu-id="9b705-369">COLUMN_FLAGS</span></span>|<span data-ttu-id="9b705-370">Int64</span><span class="sxs-lookup"><span data-stu-id="9b705-370">Int64</span></span>|  
|<span data-ttu-id="9b705-371">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="9b705-371">IS_NULLABLE</span></span>|<span data-ttu-id="9b705-372">Boolean</span><span class="sxs-lookup"><span data-stu-id="9b705-372">Boolean</span></span>|  
|<span data-ttu-id="9b705-373">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="9b705-373">DATA_TYPE</span></span>|<span data-ttu-id="9b705-374">Int32</span><span class="sxs-lookup"><span data-stu-id="9b705-374">Int32</span></span>|  
|<span data-ttu-id="9b705-375">TYPE_GUID</span><span class="sxs-lookup"><span data-stu-id="9b705-375">TYPE_GUID</span></span>|<span data-ttu-id="9b705-376">Guid</span><span class="sxs-lookup"><span data-stu-id="9b705-376">Guid</span></span>|  
|<span data-ttu-id="9b705-377">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="9b705-377">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="9b705-378">Int64</span><span class="sxs-lookup"><span data-stu-id="9b705-378">Int64</span></span>|  
|<span data-ttu-id="9b705-379">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="9b705-379">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="9b705-380">Int64</span><span class="sxs-lookup"><span data-stu-id="9b705-380">Int64</span></span>|  
|<span data-ttu-id="9b705-381">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="9b705-381">NUMERIC_PRECISION</span></span>|<span data-ttu-id="9b705-382">Int32</span><span class="sxs-lookup"><span data-stu-id="9b705-382">Int32</span></span>|  
|<span data-ttu-id="9b705-383">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="9b705-383">NUMERIC_SCALE</span></span>|<span data-ttu-id="9b705-384">Int16</span><span class="sxs-lookup"><span data-stu-id="9b705-384">Int16</span></span>|  
|<span data-ttu-id="9b705-385">DATETIME_PRECISION</span><span class="sxs-lookup"><span data-stu-id="9b705-385">DATETIME_PRECISION</span></span>|<span data-ttu-id="9b705-386">Int64</span><span class="sxs-lookup"><span data-stu-id="9b705-386">Int64</span></span>|  
|<span data-ttu-id="9b705-387">CHARACTER_SET_CATALOG</span><span class="sxs-lookup"><span data-stu-id="9b705-387">CHARACTER_SET_CATALOG</span></span>|<span data-ttu-id="9b705-388">Строковое</span><span class="sxs-lookup"><span data-stu-id="9b705-388">String</span></span>|  
|<span data-ttu-id="9b705-389">CHARACTER_SET_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="9b705-389">CHARACTER_SET_SCHEMA</span></span>|<span data-ttu-id="9b705-390">Строковое</span><span class="sxs-lookup"><span data-stu-id="9b705-390">String</span></span>|  
|<span data-ttu-id="9b705-391">CHARACTER_SET_NAME</span><span class="sxs-lookup"><span data-stu-id="9b705-391">CHARACTER_SET_NAME</span></span>|<span data-ttu-id="9b705-392">Строковое</span><span class="sxs-lookup"><span data-stu-id="9b705-392">String</span></span>|  
|<span data-ttu-id="9b705-393">COLLATION_CATALOG</span><span class="sxs-lookup"><span data-stu-id="9b705-393">COLLATION_CATALOG</span></span>|<span data-ttu-id="9b705-394">Строковое</span><span class="sxs-lookup"><span data-stu-id="9b705-394">String</span></span>|  
|<span data-ttu-id="9b705-395">COLLATION_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="9b705-395">COLLATION_SCHEMA</span></span>|<span data-ttu-id="9b705-396">Строковое</span><span class="sxs-lookup"><span data-stu-id="9b705-396">String</span></span>|  
|<span data-ttu-id="9b705-397">COLLATION_NAME</span><span class="sxs-lookup"><span data-stu-id="9b705-397">COLLATION_NAME</span></span>|<span data-ttu-id="9b705-398">Строковое</span><span class="sxs-lookup"><span data-stu-id="9b705-398">String</span></span>|  
|<span data-ttu-id="9b705-399">DOMAIN_CATALOG</span><span class="sxs-lookup"><span data-stu-id="9b705-399">DOMAIN_CATALOG</span></span>|<span data-ttu-id="9b705-400">Строковое</span><span class="sxs-lookup"><span data-stu-id="9b705-400">String</span></span>|  
|<span data-ttu-id="9b705-401">DOMAIN_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="9b705-401">DOMAIN_SCHEMA</span></span>|<span data-ttu-id="9b705-402">Строковое</span><span class="sxs-lookup"><span data-stu-id="9b705-402">String</span></span>|  
|<span data-ttu-id="9b705-403">DOMAIN_NAME</span><span class="sxs-lookup"><span data-stu-id="9b705-403">DOMAIN_NAME</span></span>|<span data-ttu-id="9b705-404">Строковое</span><span class="sxs-lookup"><span data-stu-id="9b705-404">String</span></span>|  
|<span data-ttu-id="9b705-405">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="9b705-405">DESCRIPTION</span></span>|<span data-ttu-id="9b705-406">Строковое</span><span class="sxs-lookup"><span data-stu-id="9b705-406">String</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="9b705-407">Процедуры</span><span class="sxs-lookup"><span data-stu-id="9b705-407">Procedures</span></span>  
  
|<span data-ttu-id="9b705-408">ColumnName</span><span class="sxs-lookup"><span data-stu-id="9b705-408">ColumnName</span></span>|<span data-ttu-id="9b705-409">DataType</span><span class="sxs-lookup"><span data-stu-id="9b705-409">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="9b705-410">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="9b705-410">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="9b705-411">Строковое</span><span class="sxs-lookup"><span data-stu-id="9b705-411">String</span></span>|  
|<span data-ttu-id="9b705-412">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="9b705-412">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="9b705-413">Строковое</span><span class="sxs-lookup"><span data-stu-id="9b705-413">String</span></span>|  
|<span data-ttu-id="9b705-414">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="9b705-414">PROCEDURE_NAME</span></span>|<span data-ttu-id="9b705-415">Строковое</span><span class="sxs-lookup"><span data-stu-id="9b705-415">String</span></span>|  
|<span data-ttu-id="9b705-416">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="9b705-416">PROCEDURE_TYPE</span></span>|<span data-ttu-id="9b705-417">Int16</span><span class="sxs-lookup"><span data-stu-id="9b705-417">Int16</span></span>|  
|<span data-ttu-id="9b705-418">PROCEDURE_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="9b705-418">PROCEDURE_DEFINITION</span></span>|<span data-ttu-id="9b705-419">Строковое</span><span class="sxs-lookup"><span data-stu-id="9b705-419">String</span></span>|  
|<span data-ttu-id="9b705-420">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="9b705-420">DESCRIPTION</span></span>|<span data-ttu-id="9b705-421">Строковое</span><span class="sxs-lookup"><span data-stu-id="9b705-421">String</span></span>|  
|<span data-ttu-id="9b705-422">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="9b705-422">DATE_CREATED</span></span>|<span data-ttu-id="9b705-423">DateTime</span><span class="sxs-lookup"><span data-stu-id="9b705-423">DateTime</span></span>|  
|<span data-ttu-id="9b705-424">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="9b705-424">DATE_MODIFIED</span></span>|<span data-ttu-id="9b705-425">DateTime</span><span class="sxs-lookup"><span data-stu-id="9b705-425">DateTime</span></span>|  
  
### <a name="procedurecolumns"></a><span data-ttu-id="9b705-426">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="9b705-426">ProcedureColumns</span></span>  
  
|<span data-ttu-id="9b705-427">ColumnName</span><span class="sxs-lookup"><span data-stu-id="9b705-427">ColumnName</span></span>|<span data-ttu-id="9b705-428">DataType</span><span class="sxs-lookup"><span data-stu-id="9b705-428">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="9b705-429">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="9b705-429">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="9b705-430">Строковое</span><span class="sxs-lookup"><span data-stu-id="9b705-430">String</span></span>|  
|<span data-ttu-id="9b705-431">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="9b705-431">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="9b705-432">Строковое</span><span class="sxs-lookup"><span data-stu-id="9b705-432">String</span></span>|  
|<span data-ttu-id="9b705-433">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="9b705-433">PROCEDURE_NAME</span></span>|<span data-ttu-id="9b705-434">Строковое</span><span class="sxs-lookup"><span data-stu-id="9b705-434">String</span></span>|  
|<span data-ttu-id="9b705-435">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="9b705-435">COLUMN_NAME</span></span>|<span data-ttu-id="9b705-436">Строковое</span><span class="sxs-lookup"><span data-stu-id="9b705-436">String</span></span>|  
|<span data-ttu-id="9b705-437">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="9b705-437">COLUMN_GUID</span></span>|<span data-ttu-id="9b705-438">Guid</span><span class="sxs-lookup"><span data-stu-id="9b705-438">Guid</span></span>|  
|<span data-ttu-id="9b705-439">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="9b705-439">COLUMN_PROPID</span></span>|<span data-ttu-id="9b705-440">Int64</span><span class="sxs-lookup"><span data-stu-id="9b705-440">Int64</span></span>|  
|<span data-ttu-id="9b705-441">ROWSET_NUMBER</span><span class="sxs-lookup"><span data-stu-id="9b705-441">ROWSET_NUMBER</span></span>|<span data-ttu-id="9b705-442">Int64</span><span class="sxs-lookup"><span data-stu-id="9b705-442">Int64</span></span>|  
|<span data-ttu-id="9b705-443">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="9b705-443">ORDINAL_POSITION</span></span>|<span data-ttu-id="9b705-444">Int64</span><span class="sxs-lookup"><span data-stu-id="9b705-444">Int64</span></span>|  
|<span data-ttu-id="9b705-445">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="9b705-445">IS_NULLABLE</span></span>|<span data-ttu-id="9b705-446">Boolean</span><span class="sxs-lookup"><span data-stu-id="9b705-446">Boolean</span></span>|  
|<span data-ttu-id="9b705-447">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="9b705-447">DATA_TYPE</span></span>|<span data-ttu-id="9b705-448">Int32</span><span class="sxs-lookup"><span data-stu-id="9b705-448">Int32</span></span>|  
|<span data-ttu-id="9b705-449">TYPE_GUID</span><span class="sxs-lookup"><span data-stu-id="9b705-449">TYPE_GUID</span></span>|<span data-ttu-id="9b705-450">Guid</span><span class="sxs-lookup"><span data-stu-id="9b705-450">Guid</span></span>|  
|<span data-ttu-id="9b705-451">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="9b705-451">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="9b705-452">Int64</span><span class="sxs-lookup"><span data-stu-id="9b705-452">Int64</span></span>|  
|<span data-ttu-id="9b705-453">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="9b705-453">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="9b705-454">Int64</span><span class="sxs-lookup"><span data-stu-id="9b705-454">Int64</span></span>|  
|<span data-ttu-id="9b705-455">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="9b705-455">NUMERIC_PRECISION</span></span>|<span data-ttu-id="9b705-456">Int32</span><span class="sxs-lookup"><span data-stu-id="9b705-456">Int32</span></span>|  
|<span data-ttu-id="9b705-457">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="9b705-457">NUMERIC_SCALE</span></span>|<span data-ttu-id="9b705-458">Int16</span><span class="sxs-lookup"><span data-stu-id="9b705-458">Int16</span></span>|  
|<span data-ttu-id="9b705-459">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="9b705-459">DESCRIPTION</span></span>|<span data-ttu-id="9b705-460">Строковое</span><span class="sxs-lookup"><span data-stu-id="9b705-460">String</span></span>|  
|<span data-ttu-id="9b705-461">OVERLOAD</span><span class="sxs-lookup"><span data-stu-id="9b705-461">OVERLOAD</span></span>|<span data-ttu-id="9b705-462">Int16</span><span class="sxs-lookup"><span data-stu-id="9b705-462">Int16</span></span>|  
  
### <a name="views"></a><span data-ttu-id="9b705-463">Представления</span><span class="sxs-lookup"><span data-stu-id="9b705-463">Views</span></span>  
  
|<span data-ttu-id="9b705-464">ColumnName</span><span class="sxs-lookup"><span data-stu-id="9b705-464">ColumnName</span></span>|<span data-ttu-id="9b705-465">DataType</span><span class="sxs-lookup"><span data-stu-id="9b705-465">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="9b705-466">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="9b705-466">TABLE_CATALOG</span></span>|<span data-ttu-id="9b705-467">Строковое</span><span class="sxs-lookup"><span data-stu-id="9b705-467">String</span></span>|  
|<span data-ttu-id="9b705-468">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="9b705-468">TABLE_SCHEMA</span></span>|<span data-ttu-id="9b705-469">Строковое</span><span class="sxs-lookup"><span data-stu-id="9b705-469">String</span></span>|  
|<span data-ttu-id="9b705-470">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="9b705-470">TABLE_NAME</span></span>|<span data-ttu-id="9b705-471">Строковое</span><span class="sxs-lookup"><span data-stu-id="9b705-471">String</span></span>|  
|<span data-ttu-id="9b705-472">VIEW_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="9b705-472">VIEW_DEFINITION</span></span>|<span data-ttu-id="9b705-473">Строковое</span><span class="sxs-lookup"><span data-stu-id="9b705-473">String</span></span>|  
|<span data-ttu-id="9b705-474">CHECK_OPTION</span><span class="sxs-lookup"><span data-stu-id="9b705-474">CHECK_OPTION</span></span>|<span data-ttu-id="9b705-475">Boolean</span><span class="sxs-lookup"><span data-stu-id="9b705-475">Boolean</span></span>|  
|<span data-ttu-id="9b705-476">IS_UPDATABLE</span><span class="sxs-lookup"><span data-stu-id="9b705-476">IS_UPDATABLE</span></span>|<span data-ttu-id="9b705-477">Boolean</span><span class="sxs-lookup"><span data-stu-id="9b705-477">Boolean</span></span>|  
|<span data-ttu-id="9b705-478">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="9b705-478">DESCRIPTION</span></span>|<span data-ttu-id="9b705-479">Строковое</span><span class="sxs-lookup"><span data-stu-id="9b705-479">String</span></span>|  
|<span data-ttu-id="9b705-480">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="9b705-480">DATE_CREATED</span></span>|<span data-ttu-id="9b705-481">DateTime</span><span class="sxs-lookup"><span data-stu-id="9b705-481">DateTime</span></span>|  
|<span data-ttu-id="9b705-482">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="9b705-482">DATE_MODIFIED</span></span>|<span data-ttu-id="9b705-483">DateTime</span><span class="sxs-lookup"><span data-stu-id="9b705-483">DateTime</span></span>|  
  
### <a name="indexes"></a><span data-ttu-id="9b705-484">Indexes</span><span class="sxs-lookup"><span data-stu-id="9b705-484">Indexes</span></span>  
  
|<span data-ttu-id="9b705-485">ColumnName</span><span class="sxs-lookup"><span data-stu-id="9b705-485">ColumnName</span></span>|<span data-ttu-id="9b705-486">DataType</span><span class="sxs-lookup"><span data-stu-id="9b705-486">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="9b705-487">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="9b705-487">TABLE_CATALOG</span></span>|<span data-ttu-id="9b705-488">Строковое</span><span class="sxs-lookup"><span data-stu-id="9b705-488">String</span></span>|  
|<span data-ttu-id="9b705-489">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="9b705-489">TABLE_SCHEMA</span></span>|<span data-ttu-id="9b705-490">Строковое</span><span class="sxs-lookup"><span data-stu-id="9b705-490">String</span></span>|  
|<span data-ttu-id="9b705-491">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="9b705-491">TABLE_NAME</span></span>|<span data-ttu-id="9b705-492">Строковое</span><span class="sxs-lookup"><span data-stu-id="9b705-492">String</span></span>|  
|<span data-ttu-id="9b705-493">INDEX_CATALOG</span><span class="sxs-lookup"><span data-stu-id="9b705-493">INDEX_CATALOG</span></span>|<span data-ttu-id="9b705-494">Строковое</span><span class="sxs-lookup"><span data-stu-id="9b705-494">String</span></span>|  
|<span data-ttu-id="9b705-495">INDEX_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="9b705-495">INDEX_SCHEMA</span></span>|<span data-ttu-id="9b705-496">Строковое</span><span class="sxs-lookup"><span data-stu-id="9b705-496">String</span></span>|  
|<span data-ttu-id="9b705-497">INDEX_NAME</span><span class="sxs-lookup"><span data-stu-id="9b705-497">INDEX_NAME</span></span>|<span data-ttu-id="9b705-498">Строковое</span><span class="sxs-lookup"><span data-stu-id="9b705-498">String</span></span>|  
|<span data-ttu-id="9b705-499">PRIMARY_KEY</span><span class="sxs-lookup"><span data-stu-id="9b705-499">PRIMARY_KEY</span></span>|<span data-ttu-id="9b705-500">Boolean</span><span class="sxs-lookup"><span data-stu-id="9b705-500">Boolean</span></span>|  
|<span data-ttu-id="9b705-501">UNIQUE</span><span class="sxs-lookup"><span data-stu-id="9b705-501">UNIQUE</span></span>|<span data-ttu-id="9b705-502">Boolean</span><span class="sxs-lookup"><span data-stu-id="9b705-502">Boolean</span></span>|  
|<span data-ttu-id="9b705-503">CLUSTERED</span><span class="sxs-lookup"><span data-stu-id="9b705-503">CLUSTERED</span></span>|<span data-ttu-id="9b705-504">Boolean</span><span class="sxs-lookup"><span data-stu-id="9b705-504">Boolean</span></span>|  
|<span data-ttu-id="9b705-505">TYPE</span><span class="sxs-lookup"><span data-stu-id="9b705-505">TYPE</span></span>|<span data-ttu-id="9b705-506">Int32</span><span class="sxs-lookup"><span data-stu-id="9b705-506">Int32</span></span>|  
|<span data-ttu-id="9b705-507">FILL_FACTOR</span><span class="sxs-lookup"><span data-stu-id="9b705-507">FILL_FACTOR</span></span>|<span data-ttu-id="9b705-508">Int32</span><span class="sxs-lookup"><span data-stu-id="9b705-508">Int32</span></span>|  
|<span data-ttu-id="9b705-509">INITIAL_SIZE</span><span class="sxs-lookup"><span data-stu-id="9b705-509">INITIAL_SIZE</span></span>|<span data-ttu-id="9b705-510">Int32</span><span class="sxs-lookup"><span data-stu-id="9b705-510">Int32</span></span>|  
|<span data-ttu-id="9b705-511">NULLS</span><span class="sxs-lookup"><span data-stu-id="9b705-511">NULLS</span></span>|<span data-ttu-id="9b705-512">Int32</span><span class="sxs-lookup"><span data-stu-id="9b705-512">Int32</span></span>|  
|<span data-ttu-id="9b705-513">SORT_BOOKMARKS</span><span class="sxs-lookup"><span data-stu-id="9b705-513">SORT_BOOKMARKS</span></span>|<span data-ttu-id="9b705-514">Boolean</span><span class="sxs-lookup"><span data-stu-id="9b705-514">Boolean</span></span>|  
|<span data-ttu-id="9b705-515">AUTO_UPDATE</span><span class="sxs-lookup"><span data-stu-id="9b705-515">AUTO_UPDATE</span></span>|<span data-ttu-id="9b705-516">Boolean</span><span class="sxs-lookup"><span data-stu-id="9b705-516">Boolean</span></span>|  
|<span data-ttu-id="9b705-517">NULL_COLLATION</span><span class="sxs-lookup"><span data-stu-id="9b705-517">NULL_COLLATION</span></span>|<span data-ttu-id="9b705-518">Int32</span><span class="sxs-lookup"><span data-stu-id="9b705-518">Int32</span></span>|  
|<span data-ttu-id="9b705-519">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="9b705-519">ORDINAL_POSITION</span></span>|<span data-ttu-id="9b705-520">Int64</span><span class="sxs-lookup"><span data-stu-id="9b705-520">Int64</span></span>|  
|<span data-ttu-id="9b705-521">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="9b705-521">COLUMN_NAME</span></span>|<span data-ttu-id="9b705-522">Строковое</span><span class="sxs-lookup"><span data-stu-id="9b705-522">String</span></span>|  
|<span data-ttu-id="9b705-523">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="9b705-523">COLUMN_GUID</span></span>|<span data-ttu-id="9b705-524">Guid</span><span class="sxs-lookup"><span data-stu-id="9b705-524">Guid</span></span>|  
|<span data-ttu-id="9b705-525">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="9b705-525">COLUMN_PROPID</span></span>|<span data-ttu-id="9b705-526">Int64</span><span class="sxs-lookup"><span data-stu-id="9b705-526">Int64</span></span>|  
|<span data-ttu-id="9b705-527">COLLATION</span><span class="sxs-lookup"><span data-stu-id="9b705-527">COLLATION</span></span>|<span data-ttu-id="9b705-528">Int16</span><span class="sxs-lookup"><span data-stu-id="9b705-528">Int16</span></span>|  
|<span data-ttu-id="9b705-529">CARDINALITY</span><span class="sxs-lookup"><span data-stu-id="9b705-529">CARDINALITY</span></span>|<span data-ttu-id="9b705-530">Десятичное число</span><span class="sxs-lookup"><span data-stu-id="9b705-530">Decimal</span></span>|  
|<span data-ttu-id="9b705-531">PAGES</span><span class="sxs-lookup"><span data-stu-id="9b705-531">PAGES</span></span>|<span data-ttu-id="9b705-532">Int32</span><span class="sxs-lookup"><span data-stu-id="9b705-532">Int32</span></span>|  
|<span data-ttu-id="9b705-533">FILTER_CONDITION</span><span class="sxs-lookup"><span data-stu-id="9b705-533">FILTER_CONDITION</span></span>|<span data-ttu-id="9b705-534">Строковое</span><span class="sxs-lookup"><span data-stu-id="9b705-534">String</span></span>|  
|<span data-ttu-id="9b705-535">INTEGRATED</span><span class="sxs-lookup"><span data-stu-id="9b705-535">INTEGRATED</span></span>|<span data-ttu-id="9b705-536">Boolean</span><span class="sxs-lookup"><span data-stu-id="9b705-536">Boolean</span></span>|  
  
## <a name="microsoft-jet-ole-db-provider"></a><span data-ttu-id="9b705-537">Поставщик OLE DB для Microsoft Jet</span><span class="sxs-lookup"><span data-stu-id="9b705-537">Microsoft Jet OLE DB Provider</span></span>  
 <span data-ttu-id="9b705-538">Драйвер OLE DB для Jet (Майкрософт) поддерживает следующие специальные коллекции схем в дополнение к общим коллекциям.</span><span class="sxs-lookup"><span data-stu-id="9b705-538">The Microsoft Jet OLE DB Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
-   <span data-ttu-id="9b705-539">Таблицы</span><span class="sxs-lookup"><span data-stu-id="9b705-539">Tables</span></span>  
  
-   <span data-ttu-id="9b705-540">Столбцы</span><span class="sxs-lookup"><span data-stu-id="9b705-540">Columns</span></span>  
  
-   <span data-ttu-id="9b705-541">Процедуры</span><span class="sxs-lookup"><span data-stu-id="9b705-541">Procedures</span></span>  
  
-   <span data-ttu-id="9b705-542">Представления</span><span class="sxs-lookup"><span data-stu-id="9b705-542">Views</span></span>  
  
-   <span data-ttu-id="9b705-543">Indexes</span><span class="sxs-lookup"><span data-stu-id="9b705-543">Indexes</span></span>  
  
### <a name="tables"></a><span data-ttu-id="9b705-544">Таблицы</span><span class="sxs-lookup"><span data-stu-id="9b705-544">Tables</span></span>  
  
|<span data-ttu-id="9b705-545">ColumnName</span><span class="sxs-lookup"><span data-stu-id="9b705-545">ColumnName</span></span>|<span data-ttu-id="9b705-546">DataType</span><span class="sxs-lookup"><span data-stu-id="9b705-546">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="9b705-547">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="9b705-547">TABLE_CATALOG</span></span>|<span data-ttu-id="9b705-548">Строковое</span><span class="sxs-lookup"><span data-stu-id="9b705-548">String</span></span>|  
|<span data-ttu-id="9b705-549">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="9b705-549">TABLE_SCHEMA</span></span>|<span data-ttu-id="9b705-550">Строковое</span><span class="sxs-lookup"><span data-stu-id="9b705-550">String</span></span>|  
|<span data-ttu-id="9b705-551">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="9b705-551">TABLE_NAME</span></span>|<span data-ttu-id="9b705-552">Строковое</span><span class="sxs-lookup"><span data-stu-id="9b705-552">String</span></span>|  
|<span data-ttu-id="9b705-553">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="9b705-553">TABLE_TYPE</span></span>|<span data-ttu-id="9b705-554">Строковое</span><span class="sxs-lookup"><span data-stu-id="9b705-554">String</span></span>|  
|<span data-ttu-id="9b705-555">TABLE_GUID</span><span class="sxs-lookup"><span data-stu-id="9b705-555">TABLE_GUID</span></span>|<span data-ttu-id="9b705-556">Guid</span><span class="sxs-lookup"><span data-stu-id="9b705-556">Guid</span></span>|  
|<span data-ttu-id="9b705-557">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="9b705-557">DESCRIPTION</span></span>|<span data-ttu-id="9b705-558">Строковое</span><span class="sxs-lookup"><span data-stu-id="9b705-558">String</span></span>|  
|<span data-ttu-id="9b705-559">TABLE_PROPID</span><span class="sxs-lookup"><span data-stu-id="9b705-559">TABLE_PROPID</span></span>|<span data-ttu-id="9b705-560">Int64</span><span class="sxs-lookup"><span data-stu-id="9b705-560">Int64</span></span>|  
|<span data-ttu-id="9b705-561">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="9b705-561">DATE_CREATED</span></span>|<span data-ttu-id="9b705-562">DateTime</span><span class="sxs-lookup"><span data-stu-id="9b705-562">DateTime</span></span>|  
|<span data-ttu-id="9b705-563">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="9b705-563">DATE_MODIFIED</span></span>|<span data-ttu-id="9b705-564">DateTime</span><span class="sxs-lookup"><span data-stu-id="9b705-564">DateTime</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="9b705-565">Столбцы</span><span class="sxs-lookup"><span data-stu-id="9b705-565">Columns</span></span>  
  
|<span data-ttu-id="9b705-566">ColumnName</span><span class="sxs-lookup"><span data-stu-id="9b705-566">ColumnName</span></span>|<span data-ttu-id="9b705-567">DataType</span><span class="sxs-lookup"><span data-stu-id="9b705-567">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="9b705-568">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="9b705-568">TABLE_CATALOG</span></span>|<span data-ttu-id="9b705-569">Строковое</span><span class="sxs-lookup"><span data-stu-id="9b705-569">String</span></span>|  
|<span data-ttu-id="9b705-570">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="9b705-570">TABLE_SCHEMA</span></span>|<span data-ttu-id="9b705-571">Строковое</span><span class="sxs-lookup"><span data-stu-id="9b705-571">String</span></span>|  
|<span data-ttu-id="9b705-572">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="9b705-572">TABLE_NAME</span></span>|<span data-ttu-id="9b705-573">Строковое</span><span class="sxs-lookup"><span data-stu-id="9b705-573">String</span></span>|  
|<span data-ttu-id="9b705-574">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="9b705-574">COLUMN_NAME</span></span>|<span data-ttu-id="9b705-575">Строковое</span><span class="sxs-lookup"><span data-stu-id="9b705-575">String</span></span>|  
|<span data-ttu-id="9b705-576">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="9b705-576">COLUMN_GUID</span></span>|<span data-ttu-id="9b705-577">Guid</span><span class="sxs-lookup"><span data-stu-id="9b705-577">Guid</span></span>|  
|<span data-ttu-id="9b705-578">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="9b705-578">COLUMN_PROPID</span></span>|<span data-ttu-id="9b705-579">Int64</span><span class="sxs-lookup"><span data-stu-id="9b705-579">Int64</span></span>|  
|<span data-ttu-id="9b705-580">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="9b705-580">ORDINAL_POSITION</span></span>|<span data-ttu-id="9b705-581">Int64</span><span class="sxs-lookup"><span data-stu-id="9b705-581">Int64</span></span>|  
|<span data-ttu-id="9b705-582">COLUMN_HASDEFAULT</span><span class="sxs-lookup"><span data-stu-id="9b705-582">COLUMN_HASDEFAULT</span></span>|<span data-ttu-id="9b705-583">Boolean</span><span class="sxs-lookup"><span data-stu-id="9b705-583">Boolean</span></span>|  
|<span data-ttu-id="9b705-584">COLUMN_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="9b705-584">COLUMN_DEFAULT</span></span>|<span data-ttu-id="9b705-585">Строковое</span><span class="sxs-lookup"><span data-stu-id="9b705-585">String</span></span>|  
|<span data-ttu-id="9b705-586">COLUMN_FLAGS</span><span class="sxs-lookup"><span data-stu-id="9b705-586">COLUMN_FLAGS</span></span>|<span data-ttu-id="9b705-587">Int64</span><span class="sxs-lookup"><span data-stu-id="9b705-587">Int64</span></span>|  
|<span data-ttu-id="9b705-588">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="9b705-588">IS_NULLABLE</span></span>|<span data-ttu-id="9b705-589">Boolean</span><span class="sxs-lookup"><span data-stu-id="9b705-589">Boolean</span></span>|  
|<span data-ttu-id="9b705-590">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="9b705-590">DATA_TYPE</span></span>|<span data-ttu-id="9b705-591">Int32</span><span class="sxs-lookup"><span data-stu-id="9b705-591">Int32</span></span>|  
|<span data-ttu-id="9b705-592">TYPE_GUID</span><span class="sxs-lookup"><span data-stu-id="9b705-592">TYPE_GUID</span></span>|<span data-ttu-id="9b705-593">Guid</span><span class="sxs-lookup"><span data-stu-id="9b705-593">Guid</span></span>|  
|<span data-ttu-id="9b705-594">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="9b705-594">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="9b705-595">Int64</span><span class="sxs-lookup"><span data-stu-id="9b705-595">Int64</span></span>|  
|<span data-ttu-id="9b705-596">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="9b705-596">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="9b705-597">Int64</span><span class="sxs-lookup"><span data-stu-id="9b705-597">Int64</span></span>|  
|<span data-ttu-id="9b705-598">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="9b705-598">NUMERIC_PRECISION</span></span>|<span data-ttu-id="9b705-599">Int32</span><span class="sxs-lookup"><span data-stu-id="9b705-599">Int32</span></span>|  
|<span data-ttu-id="9b705-600">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="9b705-600">NUMERIC_SCALE</span></span>|<span data-ttu-id="9b705-601">Int16</span><span class="sxs-lookup"><span data-stu-id="9b705-601">Int16</span></span>|  
|<span data-ttu-id="9b705-602">DATETIME_PRECISION</span><span class="sxs-lookup"><span data-stu-id="9b705-602">DATETIME_PRECISION</span></span>|<span data-ttu-id="9b705-603">Int64</span><span class="sxs-lookup"><span data-stu-id="9b705-603">Int64</span></span>|  
|<span data-ttu-id="9b705-604">CHARACTER_SET_CATALOG</span><span class="sxs-lookup"><span data-stu-id="9b705-604">CHARACTER_SET_CATALOG</span></span>|<span data-ttu-id="9b705-605">Строковое</span><span class="sxs-lookup"><span data-stu-id="9b705-605">String</span></span>|  
|<span data-ttu-id="9b705-606">CHARACTER_SET_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="9b705-606">CHARACTER_SET_SCHEMA</span></span>|<span data-ttu-id="9b705-607">Строковое</span><span class="sxs-lookup"><span data-stu-id="9b705-607">String</span></span>|  
|<span data-ttu-id="9b705-608">CHARACTER_SET_NAME</span><span class="sxs-lookup"><span data-stu-id="9b705-608">CHARACTER_SET_NAME</span></span>|<span data-ttu-id="9b705-609">Строковое</span><span class="sxs-lookup"><span data-stu-id="9b705-609">String</span></span>|  
|<span data-ttu-id="9b705-610">COLLATION_CATALOG</span><span class="sxs-lookup"><span data-stu-id="9b705-610">COLLATION_CATALOG</span></span>|<span data-ttu-id="9b705-611">Строковое</span><span class="sxs-lookup"><span data-stu-id="9b705-611">String</span></span>|  
|<span data-ttu-id="9b705-612">COLLATION_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="9b705-612">COLLATION_SCHEMA</span></span>|<span data-ttu-id="9b705-613">Строковое</span><span class="sxs-lookup"><span data-stu-id="9b705-613">String</span></span>|  
|<span data-ttu-id="9b705-614">COLLATION_NAME</span><span class="sxs-lookup"><span data-stu-id="9b705-614">COLLATION_NAME</span></span>|<span data-ttu-id="9b705-615">Строковое</span><span class="sxs-lookup"><span data-stu-id="9b705-615">String</span></span>|  
|<span data-ttu-id="9b705-616">DOMAIN_CATALOG</span><span class="sxs-lookup"><span data-stu-id="9b705-616">DOMAIN_CATALOG</span></span>|<span data-ttu-id="9b705-617">Строковое</span><span class="sxs-lookup"><span data-stu-id="9b705-617">String</span></span>|  
|<span data-ttu-id="9b705-618">DOMAIN_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="9b705-618">DOMAIN_SCHEMA</span></span>|<span data-ttu-id="9b705-619">Строковое</span><span class="sxs-lookup"><span data-stu-id="9b705-619">String</span></span>|  
|<span data-ttu-id="9b705-620">DOMAIN_NAME</span><span class="sxs-lookup"><span data-stu-id="9b705-620">DOMAIN_NAME</span></span>|<span data-ttu-id="9b705-621">Строковое</span><span class="sxs-lookup"><span data-stu-id="9b705-621">String</span></span>|  
|<span data-ttu-id="9b705-622">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="9b705-622">DESCRIPTION</span></span>|<span data-ttu-id="9b705-623">Строковое</span><span class="sxs-lookup"><span data-stu-id="9b705-623">String</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="9b705-624">Процедуры</span><span class="sxs-lookup"><span data-stu-id="9b705-624">Procedures</span></span>  
  
|<span data-ttu-id="9b705-625">ColumnName</span><span class="sxs-lookup"><span data-stu-id="9b705-625">ColumnName</span></span>|<span data-ttu-id="9b705-626">DataType</span><span class="sxs-lookup"><span data-stu-id="9b705-626">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="9b705-627">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="9b705-627">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="9b705-628">Строковое</span><span class="sxs-lookup"><span data-stu-id="9b705-628">String</span></span>|  
|<span data-ttu-id="9b705-629">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="9b705-629">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="9b705-630">Строковое</span><span class="sxs-lookup"><span data-stu-id="9b705-630">String</span></span>|  
|<span data-ttu-id="9b705-631">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="9b705-631">PROCEDURE_NAME</span></span>|<span data-ttu-id="9b705-632">Строковое</span><span class="sxs-lookup"><span data-stu-id="9b705-632">String</span></span>|  
|<span data-ttu-id="9b705-633">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="9b705-633">PROCEDURE_TYPE</span></span>|<span data-ttu-id="9b705-634">Int16</span><span class="sxs-lookup"><span data-stu-id="9b705-634">Int16</span></span>|  
|<span data-ttu-id="9b705-635">PROCEDURE_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="9b705-635">PROCEDURE_DEFINITION</span></span>|<span data-ttu-id="9b705-636">Строковое</span><span class="sxs-lookup"><span data-stu-id="9b705-636">String</span></span>|  
|<span data-ttu-id="9b705-637">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="9b705-637">DESCRIPTION</span></span>|<span data-ttu-id="9b705-638">Строковое</span><span class="sxs-lookup"><span data-stu-id="9b705-638">String</span></span>|  
|<span data-ttu-id="9b705-639">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="9b705-639">DATE_CREATED</span></span>|<span data-ttu-id="9b705-640">DateTime</span><span class="sxs-lookup"><span data-stu-id="9b705-640">DateTime</span></span>|  
|<span data-ttu-id="9b705-641">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="9b705-641">DATE_MODIFIED</span></span>|<span data-ttu-id="9b705-642">DateTime</span><span class="sxs-lookup"><span data-stu-id="9b705-642">DateTime</span></span>|  
  
### <a name="views"></a><span data-ttu-id="9b705-643">Представления</span><span class="sxs-lookup"><span data-stu-id="9b705-643">Views</span></span>  
  
|<span data-ttu-id="9b705-644">ColumnName</span><span class="sxs-lookup"><span data-stu-id="9b705-644">ColumnName</span></span>|<span data-ttu-id="9b705-645">DataType</span><span class="sxs-lookup"><span data-stu-id="9b705-645">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="9b705-646">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="9b705-646">TABLE_CATALOG</span></span>|<span data-ttu-id="9b705-647">Строковое</span><span class="sxs-lookup"><span data-stu-id="9b705-647">String</span></span>|  
|<span data-ttu-id="9b705-648">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="9b705-648">TABLE_SCHEMA</span></span>|<span data-ttu-id="9b705-649">Строковое</span><span class="sxs-lookup"><span data-stu-id="9b705-649">String</span></span>|  
|<span data-ttu-id="9b705-650">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="9b705-650">TABLE_NAME</span></span>|<span data-ttu-id="9b705-651">Строковое</span><span class="sxs-lookup"><span data-stu-id="9b705-651">String</span></span>|  
|<span data-ttu-id="9b705-652">VIEW_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="9b705-652">VIEW_DEFINITION</span></span>|<span data-ttu-id="9b705-653">Строковое</span><span class="sxs-lookup"><span data-stu-id="9b705-653">String</span></span>|  
|<span data-ttu-id="9b705-654">CHECK_OPTION</span><span class="sxs-lookup"><span data-stu-id="9b705-654">CHECK_OPTION</span></span>|<span data-ttu-id="9b705-655">Boolean</span><span class="sxs-lookup"><span data-stu-id="9b705-655">Boolean</span></span>|  
|<span data-ttu-id="9b705-656">IS_UPDATABLE</span><span class="sxs-lookup"><span data-stu-id="9b705-656">IS_UPDATABLE</span></span>|<span data-ttu-id="9b705-657">Boolean</span><span class="sxs-lookup"><span data-stu-id="9b705-657">Boolean</span></span>|  
|<span data-ttu-id="9b705-658">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="9b705-658">DESCRIPTION</span></span>|<span data-ttu-id="9b705-659">Строковое</span><span class="sxs-lookup"><span data-stu-id="9b705-659">String</span></span>|  
|<span data-ttu-id="9b705-660">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="9b705-660">DATE_CREATED</span></span>|<span data-ttu-id="9b705-661">DateTime</span><span class="sxs-lookup"><span data-stu-id="9b705-661">DateTime</span></span>|  
|<span data-ttu-id="9b705-662">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="9b705-662">DATE_MODIFIED</span></span>|<span data-ttu-id="9b705-663">DateTime</span><span class="sxs-lookup"><span data-stu-id="9b705-663">DateTime</span></span>|  
  
### <a name="indexes"></a><span data-ttu-id="9b705-664">Indexes</span><span class="sxs-lookup"><span data-stu-id="9b705-664">Indexes</span></span>  
  
|<span data-ttu-id="9b705-665">ColumnName</span><span class="sxs-lookup"><span data-stu-id="9b705-665">ColumnName</span></span>|<span data-ttu-id="9b705-666">DataType</span><span class="sxs-lookup"><span data-stu-id="9b705-666">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="9b705-667">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="9b705-667">TABLE_CATALOG</span></span>|<span data-ttu-id="9b705-668">Строковое</span><span class="sxs-lookup"><span data-stu-id="9b705-668">String</span></span>|  
|<span data-ttu-id="9b705-669">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="9b705-669">TABLE_SCHEMA</span></span>|<span data-ttu-id="9b705-670">Строковое</span><span class="sxs-lookup"><span data-stu-id="9b705-670">String</span></span>|  
|<span data-ttu-id="9b705-671">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="9b705-671">TABLE_NAME</span></span>|<span data-ttu-id="9b705-672">Строковое</span><span class="sxs-lookup"><span data-stu-id="9b705-672">String</span></span>|  
|<span data-ttu-id="9b705-673">INDEX_CATALOG</span><span class="sxs-lookup"><span data-stu-id="9b705-673">INDEX_CATALOG</span></span>|<span data-ttu-id="9b705-674">Строковое</span><span class="sxs-lookup"><span data-stu-id="9b705-674">String</span></span>|  
|<span data-ttu-id="9b705-675">INDEX_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="9b705-675">INDEX_SCHEMA</span></span>|<span data-ttu-id="9b705-676">Строковое</span><span class="sxs-lookup"><span data-stu-id="9b705-676">String</span></span>|  
|<span data-ttu-id="9b705-677">INDEX_NAME</span><span class="sxs-lookup"><span data-stu-id="9b705-677">INDEX_NAME</span></span>|<span data-ttu-id="9b705-678">Строковое</span><span class="sxs-lookup"><span data-stu-id="9b705-678">String</span></span>|  
|<span data-ttu-id="9b705-679">PRIMARY_KEY</span><span class="sxs-lookup"><span data-stu-id="9b705-679">PRIMARY_KEY</span></span>|<span data-ttu-id="9b705-680">Boolean</span><span class="sxs-lookup"><span data-stu-id="9b705-680">Boolean</span></span>|  
|<span data-ttu-id="9b705-681">UNIQUE</span><span class="sxs-lookup"><span data-stu-id="9b705-681">UNIQUE</span></span>|<span data-ttu-id="9b705-682">Boolean</span><span class="sxs-lookup"><span data-stu-id="9b705-682">Boolean</span></span>|  
|<span data-ttu-id="9b705-683">CLUSTERED</span><span class="sxs-lookup"><span data-stu-id="9b705-683">CLUSTERED</span></span>|<span data-ttu-id="9b705-684">Boolean</span><span class="sxs-lookup"><span data-stu-id="9b705-684">Boolean</span></span>|  
|<span data-ttu-id="9b705-685">TYPE</span><span class="sxs-lookup"><span data-stu-id="9b705-685">TYPE</span></span>|<span data-ttu-id="9b705-686">Int32</span><span class="sxs-lookup"><span data-stu-id="9b705-686">Int32</span></span>|  
|<span data-ttu-id="9b705-687">FILL_FACTOR</span><span class="sxs-lookup"><span data-stu-id="9b705-687">FILL_FACTOR</span></span>|<span data-ttu-id="9b705-688">Int32</span><span class="sxs-lookup"><span data-stu-id="9b705-688">Int32</span></span>|  
|<span data-ttu-id="9b705-689">INITIAL_SIZE</span><span class="sxs-lookup"><span data-stu-id="9b705-689">INITIAL_SIZE</span></span>|<span data-ttu-id="9b705-690">Int32</span><span class="sxs-lookup"><span data-stu-id="9b705-690">Int32</span></span>|  
|<span data-ttu-id="9b705-691">NULLS</span><span class="sxs-lookup"><span data-stu-id="9b705-691">NULLS</span></span>|<span data-ttu-id="9b705-692">Int32</span><span class="sxs-lookup"><span data-stu-id="9b705-692">Int32</span></span>|  
|<span data-ttu-id="9b705-693">SORT_BOOKMARKS</span><span class="sxs-lookup"><span data-stu-id="9b705-693">SORT_BOOKMARKS</span></span>|<span data-ttu-id="9b705-694">Boolean</span><span class="sxs-lookup"><span data-stu-id="9b705-694">Boolean</span></span>|  
|<span data-ttu-id="9b705-695">AUTO_UPDATE</span><span class="sxs-lookup"><span data-stu-id="9b705-695">AUTO_UPDATE</span></span>|<span data-ttu-id="9b705-696">Boolean</span><span class="sxs-lookup"><span data-stu-id="9b705-696">Boolean</span></span>|  
|<span data-ttu-id="9b705-697">NULL_COLLATION</span><span class="sxs-lookup"><span data-stu-id="9b705-697">NULL_COLLATION</span></span>|<span data-ttu-id="9b705-698">Int32</span><span class="sxs-lookup"><span data-stu-id="9b705-698">Int32</span></span>|  
|<span data-ttu-id="9b705-699">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="9b705-699">ORDINAL_POSITION</span></span>|<span data-ttu-id="9b705-700">Int64</span><span class="sxs-lookup"><span data-stu-id="9b705-700">Int64</span></span>|  
|<span data-ttu-id="9b705-701">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="9b705-701">COLUMN_NAME</span></span>|<span data-ttu-id="9b705-702">Строковое</span><span class="sxs-lookup"><span data-stu-id="9b705-702">String</span></span>|  
|<span data-ttu-id="9b705-703">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="9b705-703">COLUMN_GUID</span></span>|<span data-ttu-id="9b705-704">Guid</span><span class="sxs-lookup"><span data-stu-id="9b705-704">Guid</span></span>|  
|<span data-ttu-id="9b705-705">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="9b705-705">COLUMN_PROPID</span></span>|<span data-ttu-id="9b705-706">Int64</span><span class="sxs-lookup"><span data-stu-id="9b705-706">Int64</span></span>|  
|<span data-ttu-id="9b705-707">COLLATION</span><span class="sxs-lookup"><span data-stu-id="9b705-707">COLLATION</span></span>|<span data-ttu-id="9b705-708">Int16</span><span class="sxs-lookup"><span data-stu-id="9b705-708">Int16</span></span>|  
|<span data-ttu-id="9b705-709">CARDINALITY</span><span class="sxs-lookup"><span data-stu-id="9b705-709">CARDINALITY</span></span>|<span data-ttu-id="9b705-710">Десятичное число</span><span class="sxs-lookup"><span data-stu-id="9b705-710">Decimal</span></span>|  
|<span data-ttu-id="9b705-711">PAGES</span><span class="sxs-lookup"><span data-stu-id="9b705-711">PAGES</span></span>|<span data-ttu-id="9b705-712">Int32</span><span class="sxs-lookup"><span data-stu-id="9b705-712">Int32</span></span>|  
|<span data-ttu-id="9b705-713">FILTER_CONDITION</span><span class="sxs-lookup"><span data-stu-id="9b705-713">FILTER_CONDITION</span></span>|<span data-ttu-id="9b705-714">Строковое</span><span class="sxs-lookup"><span data-stu-id="9b705-714">String</span></span>|  
|<span data-ttu-id="9b705-715">INTEGRATED</span><span class="sxs-lookup"><span data-stu-id="9b705-715">INTEGRATED</span></span>|<span data-ttu-id="9b705-716">Boolean</span><span class="sxs-lookup"><span data-stu-id="9b705-716">Boolean</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="9b705-717">См. также</span><span class="sxs-lookup"><span data-stu-id="9b705-717">See Also</span></span>  
 [<span data-ttu-id="9b705-718">Центр разработчиков наборов данных и управляемых поставщиков ADO.NET</span><span class="sxs-lookup"><span data-stu-id="9b705-718">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
