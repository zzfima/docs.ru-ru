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
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 33e794559abd7f619f7431683f06e59705b57d41
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/17/2018
---
# <a name="ole-db-schema-collections"></a><span data-ttu-id="5f0ef-102">Коллекции схемы OLE DB</span><span class="sxs-lookup"><span data-stu-id="5f0ef-102">OLE DB Schema Collections</span></span>
<span data-ttu-id="5f0ef-103">В данном разделе рассматривается поддержка коллекций схем для поставщиков OLE DB для Microsoft SQL Server, Oracle и Microsoft Jet.</span><span class="sxs-lookup"><span data-stu-id="5f0ef-103">This section discusses schema collection support for the OLE DB providers for Microsoft SQL Server, Oracle, and Microsoft Jet.</span></span>  
  
## <a name="microsoft-sql-server-ole-db-provider"></a><span data-ttu-id="5f0ef-104">Поставщик OLE DB для Microsoft SQL Server</span><span class="sxs-lookup"><span data-stu-id="5f0ef-104">Microsoft SQL Server OLE DB Provider</span></span>  
 <span data-ttu-id="5f0ef-105">Драйвер Microsoft SQL Server OLE DB поддерживает следующие специальные коллекции схем в дополнение к общим коллекциям схем:</span><span class="sxs-lookup"><span data-stu-id="5f0ef-105">The Microsoft SQL Server OLE DB Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
-   <span data-ttu-id="5f0ef-106">Таблицы</span><span class="sxs-lookup"><span data-stu-id="5f0ef-106">Tables</span></span>  
  
-   <span data-ttu-id="5f0ef-107">Столбцы</span><span class="sxs-lookup"><span data-stu-id="5f0ef-107">Columns</span></span>  
  
-   <span data-ttu-id="5f0ef-108">Процедуры</span><span class="sxs-lookup"><span data-stu-id="5f0ef-108">Procedures</span></span>  
  
-   <span data-ttu-id="5f0ef-109">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="5f0ef-109">ProcedureParameters</span></span>  
  
-   <span data-ttu-id="5f0ef-110">Catalog</span><span class="sxs-lookup"><span data-stu-id="5f0ef-110">Catalog</span></span>  
  
-   <span data-ttu-id="5f0ef-111">Indexes</span><span class="sxs-lookup"><span data-stu-id="5f0ef-111">Indexes</span></span>  
  
### <a name="tables"></a><span data-ttu-id="5f0ef-112">Таблицы</span><span class="sxs-lookup"><span data-stu-id="5f0ef-112">Tables</span></span>  
  
|<span data-ttu-id="5f0ef-113">ColumnName</span><span class="sxs-lookup"><span data-stu-id="5f0ef-113">ColumnName</span></span>|<span data-ttu-id="5f0ef-114">DataType</span><span class="sxs-lookup"><span data-stu-id="5f0ef-114">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="5f0ef-115">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="5f0ef-115">TABLE_CATALOG</span></span>|<span data-ttu-id="5f0ef-116">Строковое</span><span class="sxs-lookup"><span data-stu-id="5f0ef-116">String</span></span>|  
|<span data-ttu-id="5f0ef-117">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="5f0ef-117">TABLE_SCHEMA</span></span>|<span data-ttu-id="5f0ef-118">Строковое</span><span class="sxs-lookup"><span data-stu-id="5f0ef-118">String</span></span>|  
|<span data-ttu-id="5f0ef-119">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="5f0ef-119">TABLE_NAME</span></span>|<span data-ttu-id="5f0ef-120">Строковое</span><span class="sxs-lookup"><span data-stu-id="5f0ef-120">String</span></span>|  
|<span data-ttu-id="5f0ef-121">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="5f0ef-121">TABLE_TYPE</span></span>|<span data-ttu-id="5f0ef-122">Строковое</span><span class="sxs-lookup"><span data-stu-id="5f0ef-122">String</span></span>|  
|<span data-ttu-id="5f0ef-123">TABLE_GUID</span><span class="sxs-lookup"><span data-stu-id="5f0ef-123">TABLE_GUID</span></span>|<span data-ttu-id="5f0ef-124">Guid</span><span class="sxs-lookup"><span data-stu-id="5f0ef-124">Guid</span></span>|  
|<span data-ttu-id="5f0ef-125">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="5f0ef-125">DESCRIPTION</span></span>|<span data-ttu-id="5f0ef-126">Строковое</span><span class="sxs-lookup"><span data-stu-id="5f0ef-126">String</span></span>|  
|<span data-ttu-id="5f0ef-127">TABLE_PROPID</span><span class="sxs-lookup"><span data-stu-id="5f0ef-127">TABLE_PROPID</span></span>|<span data-ttu-id="5f0ef-128">Int64</span><span class="sxs-lookup"><span data-stu-id="5f0ef-128">Int64</span></span>|  
|<span data-ttu-id="5f0ef-129">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="5f0ef-129">DATE_CREATED</span></span>|<span data-ttu-id="5f0ef-130">DateTime</span><span class="sxs-lookup"><span data-stu-id="5f0ef-130">DateTime</span></span>|  
|<span data-ttu-id="5f0ef-131">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="5f0ef-131">DATE_MODIFIED</span></span>|<span data-ttu-id="5f0ef-132">DateTime</span><span class="sxs-lookup"><span data-stu-id="5f0ef-132">DateTime</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="5f0ef-133">Столбцы</span><span class="sxs-lookup"><span data-stu-id="5f0ef-133">Columns</span></span>  
  
|<span data-ttu-id="5f0ef-134">ColumnName</span><span class="sxs-lookup"><span data-stu-id="5f0ef-134">ColumnName</span></span>|<span data-ttu-id="5f0ef-135">DataType</span><span class="sxs-lookup"><span data-stu-id="5f0ef-135">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="5f0ef-136">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="5f0ef-136">TABLE_CATALOG</span></span>|<span data-ttu-id="5f0ef-137">Строковое</span><span class="sxs-lookup"><span data-stu-id="5f0ef-137">String</span></span>|  
|<span data-ttu-id="5f0ef-138">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="5f0ef-138">TABLE_SCHEMA</span></span>|<span data-ttu-id="5f0ef-139">Строковое</span><span class="sxs-lookup"><span data-stu-id="5f0ef-139">String</span></span>|  
|<span data-ttu-id="5f0ef-140">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="5f0ef-140">TABLE_NAME</span></span>|<span data-ttu-id="5f0ef-141">Строковое</span><span class="sxs-lookup"><span data-stu-id="5f0ef-141">String</span></span>|  
|<span data-ttu-id="5f0ef-142">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="5f0ef-142">COLUMN_NAME</span></span>|<span data-ttu-id="5f0ef-143">Строковое</span><span class="sxs-lookup"><span data-stu-id="5f0ef-143">String</span></span>|  
|<span data-ttu-id="5f0ef-144">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="5f0ef-144">COLUMN_GUID</span></span>|<span data-ttu-id="5f0ef-145">Guid</span><span class="sxs-lookup"><span data-stu-id="5f0ef-145">Guid</span></span>|  
|<span data-ttu-id="5f0ef-146">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="5f0ef-146">COLUMN_PROPID</span></span>|<span data-ttu-id="5f0ef-147">Int64</span><span class="sxs-lookup"><span data-stu-id="5f0ef-147">Int64</span></span>|  
|<span data-ttu-id="5f0ef-148">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="5f0ef-148">ORDINAL_POSITION</span></span>|<span data-ttu-id="5f0ef-149">Int64</span><span class="sxs-lookup"><span data-stu-id="5f0ef-149">Int64</span></span>|  
|<span data-ttu-id="5f0ef-150">COLUMN_HASDEFAULT</span><span class="sxs-lookup"><span data-stu-id="5f0ef-150">COLUMN_HASDEFAULT</span></span>|<span data-ttu-id="5f0ef-151">Boolean</span><span class="sxs-lookup"><span data-stu-id="5f0ef-151">Boolean</span></span>|  
|<span data-ttu-id="5f0ef-152">COLUMN_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="5f0ef-152">COLUMN_DEFAULT</span></span>|<span data-ttu-id="5f0ef-153">Строковое</span><span class="sxs-lookup"><span data-stu-id="5f0ef-153">String</span></span>|  
|<span data-ttu-id="5f0ef-154">COLUMN_FLAGS</span><span class="sxs-lookup"><span data-stu-id="5f0ef-154">COLUMN_FLAGS</span></span>|<span data-ttu-id="5f0ef-155">Int64</span><span class="sxs-lookup"><span data-stu-id="5f0ef-155">Int64</span></span>|  
|<span data-ttu-id="5f0ef-156">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="5f0ef-156">IS_NULLABLE</span></span>|<span data-ttu-id="5f0ef-157">Boolean</span><span class="sxs-lookup"><span data-stu-id="5f0ef-157">Boolean</span></span>|  
|<span data-ttu-id="5f0ef-158">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="5f0ef-158">DATA_TYPE</span></span>|<span data-ttu-id="5f0ef-159">Int32</span><span class="sxs-lookup"><span data-stu-id="5f0ef-159">Int32</span></span>|  
|<span data-ttu-id="5f0ef-160">TYPE_GUID</span><span class="sxs-lookup"><span data-stu-id="5f0ef-160">TYPE_GUID</span></span>|<span data-ttu-id="5f0ef-161">Guid</span><span class="sxs-lookup"><span data-stu-id="5f0ef-161">Guid</span></span>|  
|<span data-ttu-id="5f0ef-162">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="5f0ef-162">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="5f0ef-163">Int64</span><span class="sxs-lookup"><span data-stu-id="5f0ef-163">Int64</span></span>|  
|<span data-ttu-id="5f0ef-164">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="5f0ef-164">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="5f0ef-165">Int64</span><span class="sxs-lookup"><span data-stu-id="5f0ef-165">Int64</span></span>|  
|<span data-ttu-id="5f0ef-166">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="5f0ef-166">NUMERIC_PRECISION</span></span>|<span data-ttu-id="5f0ef-167">Int32</span><span class="sxs-lookup"><span data-stu-id="5f0ef-167">Int32</span></span>|  
|<span data-ttu-id="5f0ef-168">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="5f0ef-168">NUMERIC_SCALE</span></span>|<span data-ttu-id="5f0ef-169">Int16</span><span class="sxs-lookup"><span data-stu-id="5f0ef-169">Int16</span></span>|  
|<span data-ttu-id="5f0ef-170">DATETIME_PRECISION</span><span class="sxs-lookup"><span data-stu-id="5f0ef-170">DATETIME_PRECISION</span></span>|<span data-ttu-id="5f0ef-171">Int64</span><span class="sxs-lookup"><span data-stu-id="5f0ef-171">Int64</span></span>|  
|<span data-ttu-id="5f0ef-172">CHARACTER_SET_CATALOG</span><span class="sxs-lookup"><span data-stu-id="5f0ef-172">CHARACTER_SET_CATALOG</span></span>|<span data-ttu-id="5f0ef-173">Строковое</span><span class="sxs-lookup"><span data-stu-id="5f0ef-173">String</span></span>|  
|<span data-ttu-id="5f0ef-174">CHARACTER_SET_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="5f0ef-174">CHARACTER_SET_SCHEMA</span></span>|<span data-ttu-id="5f0ef-175">Строковое</span><span class="sxs-lookup"><span data-stu-id="5f0ef-175">String</span></span>|  
|<span data-ttu-id="5f0ef-176">CHARACTER_SET_NAME</span><span class="sxs-lookup"><span data-stu-id="5f0ef-176">CHARACTER_SET_NAME</span></span>|<span data-ttu-id="5f0ef-177">Строковое</span><span class="sxs-lookup"><span data-stu-id="5f0ef-177">String</span></span>|  
|<span data-ttu-id="5f0ef-178">COLLATION_CATALOG</span><span class="sxs-lookup"><span data-stu-id="5f0ef-178">COLLATION_CATALOG</span></span>|<span data-ttu-id="5f0ef-179">Строковое</span><span class="sxs-lookup"><span data-stu-id="5f0ef-179">String</span></span>|  
|<span data-ttu-id="5f0ef-180">COLLATION_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="5f0ef-180">COLLATION_SCHEMA</span></span>|<span data-ttu-id="5f0ef-181">Строковое</span><span class="sxs-lookup"><span data-stu-id="5f0ef-181">String</span></span>|  
|<span data-ttu-id="5f0ef-182">COLLATION_NAME</span><span class="sxs-lookup"><span data-stu-id="5f0ef-182">COLLATION_NAME</span></span>|<span data-ttu-id="5f0ef-183">Строковое</span><span class="sxs-lookup"><span data-stu-id="5f0ef-183">String</span></span>|  
|<span data-ttu-id="5f0ef-184">DOMAIN_CATALOG</span><span class="sxs-lookup"><span data-stu-id="5f0ef-184">DOMAIN_CATALOG</span></span>|<span data-ttu-id="5f0ef-185">Строковое</span><span class="sxs-lookup"><span data-stu-id="5f0ef-185">String</span></span>|  
|<span data-ttu-id="5f0ef-186">DOMAIN_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="5f0ef-186">DOMAIN_SCHEMA</span></span>|<span data-ttu-id="5f0ef-187">Строковое</span><span class="sxs-lookup"><span data-stu-id="5f0ef-187">String</span></span>|  
|<span data-ttu-id="5f0ef-188">DOMAIN_NAME</span><span class="sxs-lookup"><span data-stu-id="5f0ef-188">DOMAIN_NAME</span></span>|<span data-ttu-id="5f0ef-189">Строковое</span><span class="sxs-lookup"><span data-stu-id="5f0ef-189">String</span></span>|  
|<span data-ttu-id="5f0ef-190">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="5f0ef-190">DESCRIPTION</span></span>|<span data-ttu-id="5f0ef-191">Строковое</span><span class="sxs-lookup"><span data-stu-id="5f0ef-191">String</span></span>|  
|<span data-ttu-id="5f0ef-192">COLUMN_LCID</span><span class="sxs-lookup"><span data-stu-id="5f0ef-192">COLUMN_LCID</span></span>|<span data-ttu-id="5f0ef-193">Int32</span><span class="sxs-lookup"><span data-stu-id="5f0ef-193">Int32</span></span>|  
|<span data-ttu-id="5f0ef-194">COLUMN_COMPFLAGS</span><span class="sxs-lookup"><span data-stu-id="5f0ef-194">COLUMN_COMPFLAGS</span></span>|<span data-ttu-id="5f0ef-195">Int32</span><span class="sxs-lookup"><span data-stu-id="5f0ef-195">Int32</span></span>|  
|<span data-ttu-id="5f0ef-196">COLUMN_SORTID</span><span class="sxs-lookup"><span data-stu-id="5f0ef-196">COLUMN_SORTID</span></span>|<span data-ttu-id="5f0ef-197">Int32</span><span class="sxs-lookup"><span data-stu-id="5f0ef-197">Int32</span></span>|  
|<span data-ttu-id="5f0ef-198">COLUMN_TDSCOLLATION</span><span class="sxs-lookup"><span data-stu-id="5f0ef-198">COLUMN_TDSCOLLATION</span></span>|<span data-ttu-id="5f0ef-199">Byte[]</span><span class="sxs-lookup"><span data-stu-id="5f0ef-199">Byte[]</span></span>|  
|<span data-ttu-id="5f0ef-200">IS_COMPUTED</span><span class="sxs-lookup"><span data-stu-id="5f0ef-200">IS_COMPUTED</span></span>|<span data-ttu-id="5f0ef-201">Boolean</span><span class="sxs-lookup"><span data-stu-id="5f0ef-201">Boolean</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="5f0ef-202">Процедуры</span><span class="sxs-lookup"><span data-stu-id="5f0ef-202">Procedures</span></span>  
  
|<span data-ttu-id="5f0ef-203">ColumnName</span><span class="sxs-lookup"><span data-stu-id="5f0ef-203">ColumnName</span></span>|<span data-ttu-id="5f0ef-204">DataType</span><span class="sxs-lookup"><span data-stu-id="5f0ef-204">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="5f0ef-205">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="5f0ef-205">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="5f0ef-206">Строковое</span><span class="sxs-lookup"><span data-stu-id="5f0ef-206">String</span></span>|  
|<span data-ttu-id="5f0ef-207">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="5f0ef-207">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="5f0ef-208">Строковое</span><span class="sxs-lookup"><span data-stu-id="5f0ef-208">String</span></span>|  
|<span data-ttu-id="5f0ef-209">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="5f0ef-209">PROCEDURE_NAME</span></span>|<span data-ttu-id="5f0ef-210">Строковое</span><span class="sxs-lookup"><span data-stu-id="5f0ef-210">String</span></span>|  
|<span data-ttu-id="5f0ef-211">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="5f0ef-211">PROCEDURE_TYPE</span></span>|<span data-ttu-id="5f0ef-212">Int16</span><span class="sxs-lookup"><span data-stu-id="5f0ef-212">Int16</span></span>|  
|<span data-ttu-id="5f0ef-213">PROCEDURE_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="5f0ef-213">PROCEDURE_DEFINITION</span></span>|<span data-ttu-id="5f0ef-214">Строковое</span><span class="sxs-lookup"><span data-stu-id="5f0ef-214">String</span></span>|  
|<span data-ttu-id="5f0ef-215">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="5f0ef-215">DESCRIPTION</span></span>|<span data-ttu-id="5f0ef-216">Строковое</span><span class="sxs-lookup"><span data-stu-id="5f0ef-216">String</span></span>|  
|<span data-ttu-id="5f0ef-217">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="5f0ef-217">DATE_CREATED</span></span>|<span data-ttu-id="5f0ef-218">DateTime</span><span class="sxs-lookup"><span data-stu-id="5f0ef-218">DateTime</span></span>|  
|<span data-ttu-id="5f0ef-219">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="5f0ef-219">DATE_MODIFIED</span></span>|<span data-ttu-id="5f0ef-220">DateTime</span><span class="sxs-lookup"><span data-stu-id="5f0ef-220">DateTime</span></span>|  
  
### <a name="procedureparameters"></a><span data-ttu-id="5f0ef-221">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="5f0ef-221">ProcedureParameters</span></span>  
  
|<span data-ttu-id="5f0ef-222">ColumnName</span><span class="sxs-lookup"><span data-stu-id="5f0ef-222">ColumnName</span></span>|<span data-ttu-id="5f0ef-223">DataType</span><span class="sxs-lookup"><span data-stu-id="5f0ef-223">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="5f0ef-224">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="5f0ef-224">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="5f0ef-225">Строковое</span><span class="sxs-lookup"><span data-stu-id="5f0ef-225">String</span></span>|  
|<span data-ttu-id="5f0ef-226">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="5f0ef-226">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="5f0ef-227">Строковое</span><span class="sxs-lookup"><span data-stu-id="5f0ef-227">String</span></span>|  
|<span data-ttu-id="5f0ef-228">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="5f0ef-228">PROCEDURE_NAME</span></span>|<span data-ttu-id="5f0ef-229">Строковое</span><span class="sxs-lookup"><span data-stu-id="5f0ef-229">String</span></span>|  
|<span data-ttu-id="5f0ef-230">PARAMETER_NAME</span><span class="sxs-lookup"><span data-stu-id="5f0ef-230">PARAMETER_NAME</span></span>|<span data-ttu-id="5f0ef-231">Строковое</span><span class="sxs-lookup"><span data-stu-id="5f0ef-231">String</span></span>|  
|<span data-ttu-id="5f0ef-232">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="5f0ef-232">ORDINAL_POSITION</span></span>|<span data-ttu-id="5f0ef-233">Int32</span><span class="sxs-lookup"><span data-stu-id="5f0ef-233">Int32</span></span>|  
|<span data-ttu-id="5f0ef-234">PARAMETER_TYPE</span><span class="sxs-lookup"><span data-stu-id="5f0ef-234">PARAMETER_TYPE</span></span>|<span data-ttu-id="5f0ef-235">Int32</span><span class="sxs-lookup"><span data-stu-id="5f0ef-235">Int32</span></span>|  
|<span data-ttu-id="5f0ef-236">PARAMETER_HASDEFAULT</span><span class="sxs-lookup"><span data-stu-id="5f0ef-236">PARAMETER_HASDEFAULT</span></span>|<span data-ttu-id="5f0ef-237">Boolean</span><span class="sxs-lookup"><span data-stu-id="5f0ef-237">Boolean</span></span>|  
|<span data-ttu-id="5f0ef-238">PARAMETER_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="5f0ef-238">PARAMETER_DEFAULT</span></span>|<span data-ttu-id="5f0ef-239">Строковое</span><span class="sxs-lookup"><span data-stu-id="5f0ef-239">String</span></span>|  
|<span data-ttu-id="5f0ef-240">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="5f0ef-240">IS_NULLABLE</span></span>|<span data-ttu-id="5f0ef-241">Boolean</span><span class="sxs-lookup"><span data-stu-id="5f0ef-241">Boolean</span></span>|  
|<span data-ttu-id="5f0ef-242">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="5f0ef-242">DATA_TYPE</span></span>|<span data-ttu-id="5f0ef-243">Int32</span><span class="sxs-lookup"><span data-stu-id="5f0ef-243">Int32</span></span>|  
|<span data-ttu-id="5f0ef-244">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="5f0ef-244">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="5f0ef-245">Int64</span><span class="sxs-lookup"><span data-stu-id="5f0ef-245">Int64</span></span>|  
|<span data-ttu-id="5f0ef-246">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="5f0ef-246">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="5f0ef-247">Int64</span><span class="sxs-lookup"><span data-stu-id="5f0ef-247">Int64</span></span>|  
|<span data-ttu-id="5f0ef-248">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="5f0ef-248">NUMERIC_PRECISION</span></span>|<span data-ttu-id="5f0ef-249">Int32</span><span class="sxs-lookup"><span data-stu-id="5f0ef-249">Int32</span></span>|  
|<span data-ttu-id="5f0ef-250">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="5f0ef-250">NUMERIC_SCALE</span></span>|<span data-ttu-id="5f0ef-251">Int16</span><span class="sxs-lookup"><span data-stu-id="5f0ef-251">Int16</span></span>|  
|<span data-ttu-id="5f0ef-252">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="5f0ef-252">DESCRIPTION</span></span>|<span data-ttu-id="5f0ef-253">Строковое</span><span class="sxs-lookup"><span data-stu-id="5f0ef-253">String</span></span>|  
|<span data-ttu-id="5f0ef-254">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="5f0ef-254">TYPE_NAME</span></span>|<span data-ttu-id="5f0ef-255">Строковое</span><span class="sxs-lookup"><span data-stu-id="5f0ef-255">String</span></span>|  
|<span data-ttu-id="5f0ef-256">LOCAL_TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="5f0ef-256">LOCAL_TYPE_NAME</span></span>|<span data-ttu-id="5f0ef-257">Строковое</span><span class="sxs-lookup"><span data-stu-id="5f0ef-257">String</span></span>|  
  
### <a name="catalog"></a><span data-ttu-id="5f0ef-258">Catalog</span><span class="sxs-lookup"><span data-stu-id="5f0ef-258">Catalog</span></span>  
  
|<span data-ttu-id="5f0ef-259">ColumnName</span><span class="sxs-lookup"><span data-stu-id="5f0ef-259">ColumnName</span></span>|<span data-ttu-id="5f0ef-260">DataType</span><span class="sxs-lookup"><span data-stu-id="5f0ef-260">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="5f0ef-261">CATALOG_NAME</span><span class="sxs-lookup"><span data-stu-id="5f0ef-261">CATALOG_NAME</span></span>|<span data-ttu-id="5f0ef-262">Строковое</span><span class="sxs-lookup"><span data-stu-id="5f0ef-262">String</span></span>|  
|<span data-ttu-id="5f0ef-263">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="5f0ef-263">DESCRIPTION</span></span>|<span data-ttu-id="5f0ef-264">Строковое</span><span class="sxs-lookup"><span data-stu-id="5f0ef-264">String</span></span>|  
  
### <a name="indexes"></a><span data-ttu-id="5f0ef-265">Indexes</span><span class="sxs-lookup"><span data-stu-id="5f0ef-265">Indexes</span></span>  
  
|<span data-ttu-id="5f0ef-266">ColumnName</span><span class="sxs-lookup"><span data-stu-id="5f0ef-266">ColumnName</span></span>|<span data-ttu-id="5f0ef-267">DataType</span><span class="sxs-lookup"><span data-stu-id="5f0ef-267">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="5f0ef-268">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="5f0ef-268">TABLE_CATALOG</span></span>|<span data-ttu-id="5f0ef-269">Строковое</span><span class="sxs-lookup"><span data-stu-id="5f0ef-269">String</span></span>|  
|<span data-ttu-id="5f0ef-270">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="5f0ef-270">TABLE_SCHEMA</span></span>|<span data-ttu-id="5f0ef-271">Строковое</span><span class="sxs-lookup"><span data-stu-id="5f0ef-271">String</span></span>|  
|<span data-ttu-id="5f0ef-272">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="5f0ef-272">TABLE_NAME</span></span>|<span data-ttu-id="5f0ef-273">Строковое</span><span class="sxs-lookup"><span data-stu-id="5f0ef-273">String</span></span>|  
|<span data-ttu-id="5f0ef-274">INDEX_CATALOG</span><span class="sxs-lookup"><span data-stu-id="5f0ef-274">INDEX_CATALOG</span></span>|<span data-ttu-id="5f0ef-275">Строковое</span><span class="sxs-lookup"><span data-stu-id="5f0ef-275">String</span></span>|  
|<span data-ttu-id="5f0ef-276">INDEX_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="5f0ef-276">INDEX_SCHEMA</span></span>|<span data-ttu-id="5f0ef-277">Строковое</span><span class="sxs-lookup"><span data-stu-id="5f0ef-277">String</span></span>|  
|<span data-ttu-id="5f0ef-278">INDEX_NAME</span><span class="sxs-lookup"><span data-stu-id="5f0ef-278">INDEX_NAME</span></span>|<span data-ttu-id="5f0ef-279">Строковое</span><span class="sxs-lookup"><span data-stu-id="5f0ef-279">String</span></span>|  
|<span data-ttu-id="5f0ef-280">PRIMARY_KEY</span><span class="sxs-lookup"><span data-stu-id="5f0ef-280">PRIMARY_KEY</span></span>|<span data-ttu-id="5f0ef-281">Boolean</span><span class="sxs-lookup"><span data-stu-id="5f0ef-281">Boolean</span></span>|  
|<span data-ttu-id="5f0ef-282">UNIQUE</span><span class="sxs-lookup"><span data-stu-id="5f0ef-282">UNIQUE</span></span>|<span data-ttu-id="5f0ef-283">Boolean</span><span class="sxs-lookup"><span data-stu-id="5f0ef-283">Boolean</span></span>|  
|<span data-ttu-id="5f0ef-284">CLUSTERED</span><span class="sxs-lookup"><span data-stu-id="5f0ef-284">CLUSTERED</span></span>|<span data-ttu-id="5f0ef-285">Boolean</span><span class="sxs-lookup"><span data-stu-id="5f0ef-285">Boolean</span></span>|  
|<span data-ttu-id="5f0ef-286">TYPE</span><span class="sxs-lookup"><span data-stu-id="5f0ef-286">TYPE</span></span>|<span data-ttu-id="5f0ef-287">Int32</span><span class="sxs-lookup"><span data-stu-id="5f0ef-287">Int32</span></span>|  
|<span data-ttu-id="5f0ef-288">FILL_FACTOR</span><span class="sxs-lookup"><span data-stu-id="5f0ef-288">FILL_FACTOR</span></span>|<span data-ttu-id="5f0ef-289">Int32</span><span class="sxs-lookup"><span data-stu-id="5f0ef-289">Int32</span></span>|  
|<span data-ttu-id="5f0ef-290">INITIAL_SIZE</span><span class="sxs-lookup"><span data-stu-id="5f0ef-290">INITIAL_SIZE</span></span>|<span data-ttu-id="5f0ef-291">Int32</span><span class="sxs-lookup"><span data-stu-id="5f0ef-291">Int32</span></span>|  
|<span data-ttu-id="5f0ef-292">NULLS</span><span class="sxs-lookup"><span data-stu-id="5f0ef-292">NULLS</span></span>|<span data-ttu-id="5f0ef-293">Int32</span><span class="sxs-lookup"><span data-stu-id="5f0ef-293">Int32</span></span>|  
|<span data-ttu-id="5f0ef-294">SORT_BOOKMARKS</span><span class="sxs-lookup"><span data-stu-id="5f0ef-294">SORT_BOOKMARKS</span></span>|<span data-ttu-id="5f0ef-295">Boolean</span><span class="sxs-lookup"><span data-stu-id="5f0ef-295">Boolean</span></span>|  
|<span data-ttu-id="5f0ef-296">AUTO_UPDATE</span><span class="sxs-lookup"><span data-stu-id="5f0ef-296">AUTO_UPDATE</span></span>|<span data-ttu-id="5f0ef-297">Boolean</span><span class="sxs-lookup"><span data-stu-id="5f0ef-297">Boolean</span></span>|  
|<span data-ttu-id="5f0ef-298">NULL_COLLATION</span><span class="sxs-lookup"><span data-stu-id="5f0ef-298">NULL_COLLATION</span></span>|<span data-ttu-id="5f0ef-299">Int32</span><span class="sxs-lookup"><span data-stu-id="5f0ef-299">Int32</span></span>|  
|<span data-ttu-id="5f0ef-300">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="5f0ef-300">ORDINAL_POSITION</span></span>|<span data-ttu-id="5f0ef-301">Int64</span><span class="sxs-lookup"><span data-stu-id="5f0ef-301">Int64</span></span>|  
|<span data-ttu-id="5f0ef-302">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="5f0ef-302">COLUMN_NAME</span></span>|<span data-ttu-id="5f0ef-303">Строковое</span><span class="sxs-lookup"><span data-stu-id="5f0ef-303">String</span></span>|  
|<span data-ttu-id="5f0ef-304">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="5f0ef-304">COLUMN_GUID</span></span>|<span data-ttu-id="5f0ef-305">Guid</span><span class="sxs-lookup"><span data-stu-id="5f0ef-305">Guid</span></span>|  
|<span data-ttu-id="5f0ef-306">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="5f0ef-306">COLUMN_PROPID</span></span>|<span data-ttu-id="5f0ef-307">Int64</span><span class="sxs-lookup"><span data-stu-id="5f0ef-307">Int64</span></span>|  
|<span data-ttu-id="5f0ef-308">COLLATION</span><span class="sxs-lookup"><span data-stu-id="5f0ef-308">COLLATION</span></span>|<span data-ttu-id="5f0ef-309">Int16</span><span class="sxs-lookup"><span data-stu-id="5f0ef-309">Int16</span></span>|  
|<span data-ttu-id="5f0ef-310">CARDINALITY</span><span class="sxs-lookup"><span data-stu-id="5f0ef-310">CARDINALITY</span></span>|<span data-ttu-id="5f0ef-311">Десятичное число</span><span class="sxs-lookup"><span data-stu-id="5f0ef-311">Decimal</span></span>|  
|<span data-ttu-id="5f0ef-312">PAGES</span><span class="sxs-lookup"><span data-stu-id="5f0ef-312">PAGES</span></span>|<span data-ttu-id="5f0ef-313">Int32</span><span class="sxs-lookup"><span data-stu-id="5f0ef-313">Int32</span></span>|  
|<span data-ttu-id="5f0ef-314">FILTER_CONDITION</span><span class="sxs-lookup"><span data-stu-id="5f0ef-314">FILTER_CONDITION</span></span>|<span data-ttu-id="5f0ef-315">Строковое</span><span class="sxs-lookup"><span data-stu-id="5f0ef-315">String</span></span>|  
|<span data-ttu-id="5f0ef-316">INTEGRATED</span><span class="sxs-lookup"><span data-stu-id="5f0ef-316">INTEGRATED</span></span>|<span data-ttu-id="5f0ef-317">Boolean</span><span class="sxs-lookup"><span data-stu-id="5f0ef-317">Boolean</span></span>|  
  
## <a name="microsoft-oracle-ole-db-provider"></a><span data-ttu-id="5f0ef-318">Поставщик Microsoft OLE DB для Oracle</span><span class="sxs-lookup"><span data-stu-id="5f0ef-318">Microsoft Oracle OLE DB Provider</span></span>  
 <span data-ttu-id="5f0ef-319">Драйвер OLE DB для Oracle (Майкрософт) поддерживает следующие специальные коллекции схем в дополнение к общим коллекциям.</span><span class="sxs-lookup"><span data-stu-id="5f0ef-319">The Microsoft Oracle OLE DB Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
-   <span data-ttu-id="5f0ef-320">Таблицы</span><span class="sxs-lookup"><span data-stu-id="5f0ef-320">Tables</span></span>  
  
-   <span data-ttu-id="5f0ef-321">Столбцы</span><span class="sxs-lookup"><span data-stu-id="5f0ef-321">Columns</span></span>  
  
-   <span data-ttu-id="5f0ef-322">Процедуры</span><span class="sxs-lookup"><span data-stu-id="5f0ef-322">Procedures</span></span>  
  
-   <span data-ttu-id="5f0ef-323">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="5f0ef-323">ProcedureColumns</span></span>  
  
-   <span data-ttu-id="5f0ef-324">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="5f0ef-324">ProcedureParameters</span></span>  
  
-   <span data-ttu-id="5f0ef-325">Представления</span><span class="sxs-lookup"><span data-stu-id="5f0ef-325">Views</span></span>  
  
-   <span data-ttu-id="5f0ef-326">Indexes</span><span class="sxs-lookup"><span data-stu-id="5f0ef-326">Indexes</span></span>  
  
### <a name="tables"></a><span data-ttu-id="5f0ef-327">Таблицы</span><span class="sxs-lookup"><span data-stu-id="5f0ef-327">Tables</span></span>  
  
|<span data-ttu-id="5f0ef-328">ColumnName</span><span class="sxs-lookup"><span data-stu-id="5f0ef-328">ColumnName</span></span>|<span data-ttu-id="5f0ef-329">DataType</span><span class="sxs-lookup"><span data-stu-id="5f0ef-329">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="5f0ef-330">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="5f0ef-330">TABLE_CATALOG</span></span>|<span data-ttu-id="5f0ef-331">Строковое</span><span class="sxs-lookup"><span data-stu-id="5f0ef-331">String</span></span>|  
|<span data-ttu-id="5f0ef-332">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="5f0ef-332">TABLE_SCHEMA</span></span>|<span data-ttu-id="5f0ef-333">Строковое</span><span class="sxs-lookup"><span data-stu-id="5f0ef-333">String</span></span>|  
|<span data-ttu-id="5f0ef-334">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="5f0ef-334">TABLE_NAME</span></span>|<span data-ttu-id="5f0ef-335">Строковое</span><span class="sxs-lookup"><span data-stu-id="5f0ef-335">String</span></span>|  
|<span data-ttu-id="5f0ef-336">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="5f0ef-336">TABLE_TYPE</span></span>|<span data-ttu-id="5f0ef-337">Строковое</span><span class="sxs-lookup"><span data-stu-id="5f0ef-337">String</span></span>|  
|<span data-ttu-id="5f0ef-338">TABLE_GUID</span><span class="sxs-lookup"><span data-stu-id="5f0ef-338">TABLE_GUID</span></span>|<span data-ttu-id="5f0ef-339">Guid</span><span class="sxs-lookup"><span data-stu-id="5f0ef-339">Guid</span></span>|  
|<span data-ttu-id="5f0ef-340">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="5f0ef-340">DESCRIPTION</span></span>|<span data-ttu-id="5f0ef-341">Строковое</span><span class="sxs-lookup"><span data-stu-id="5f0ef-341">String</span></span>|  
|<span data-ttu-id="5f0ef-342">TABLE_PROPID</span><span class="sxs-lookup"><span data-stu-id="5f0ef-342">TABLE_PROPID</span></span>|<span data-ttu-id="5f0ef-343">Int64</span><span class="sxs-lookup"><span data-stu-id="5f0ef-343">Int64</span></span>|  
|<span data-ttu-id="5f0ef-344">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="5f0ef-344">DATE_CREATED</span></span>|<span data-ttu-id="5f0ef-345">DateTime</span><span class="sxs-lookup"><span data-stu-id="5f0ef-345">DateTime</span></span>|  
|<span data-ttu-id="5f0ef-346">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="5f0ef-346">DATE_MODIFIED</span></span>|<span data-ttu-id="5f0ef-347">DateTime</span><span class="sxs-lookup"><span data-stu-id="5f0ef-347">DateTime</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="5f0ef-348">Столбцы</span><span class="sxs-lookup"><span data-stu-id="5f0ef-348">Columns</span></span>  
  
|<span data-ttu-id="5f0ef-349">ColumnName</span><span class="sxs-lookup"><span data-stu-id="5f0ef-349">ColumnName</span></span>|<span data-ttu-id="5f0ef-350">DataType</span><span class="sxs-lookup"><span data-stu-id="5f0ef-350">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="5f0ef-351">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="5f0ef-351">TABLE_CATALOG</span></span>|<span data-ttu-id="5f0ef-352">Строковое</span><span class="sxs-lookup"><span data-stu-id="5f0ef-352">String</span></span>|  
|<span data-ttu-id="5f0ef-353">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="5f0ef-353">TABLE_SCHEMA</span></span>|<span data-ttu-id="5f0ef-354">Строковое</span><span class="sxs-lookup"><span data-stu-id="5f0ef-354">String</span></span>|  
|<span data-ttu-id="5f0ef-355">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="5f0ef-355">TABLE_NAME</span></span>|<span data-ttu-id="5f0ef-356">Строковое</span><span class="sxs-lookup"><span data-stu-id="5f0ef-356">String</span></span>|  
|<span data-ttu-id="5f0ef-357">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="5f0ef-357">COLUMN_NAME</span></span>|<span data-ttu-id="5f0ef-358">Строковое</span><span class="sxs-lookup"><span data-stu-id="5f0ef-358">String</span></span>|  
|<span data-ttu-id="5f0ef-359">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="5f0ef-359">COLUMN_GUID</span></span>|<span data-ttu-id="5f0ef-360">Guid</span><span class="sxs-lookup"><span data-stu-id="5f0ef-360">Guid</span></span>|  
|<span data-ttu-id="5f0ef-361">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="5f0ef-361">COLUMN_PROPID</span></span>|<span data-ttu-id="5f0ef-362">Int64</span><span class="sxs-lookup"><span data-stu-id="5f0ef-362">Int64</span></span>|  
|<span data-ttu-id="5f0ef-363">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="5f0ef-363">ORDINAL_POSITION</span></span>|<span data-ttu-id="5f0ef-364">Int64</span><span class="sxs-lookup"><span data-stu-id="5f0ef-364">Int64</span></span>|  
|<span data-ttu-id="5f0ef-365">COLUMN_HASDEFAULT</span><span class="sxs-lookup"><span data-stu-id="5f0ef-365">COLUMN_HASDEFAULT</span></span>|<span data-ttu-id="5f0ef-366">Boolean</span><span class="sxs-lookup"><span data-stu-id="5f0ef-366">Boolean</span></span>|  
|<span data-ttu-id="5f0ef-367">COLUMN_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="5f0ef-367">COLUMN_DEFAULT</span></span>|<span data-ttu-id="5f0ef-368">Строковое</span><span class="sxs-lookup"><span data-stu-id="5f0ef-368">String</span></span>|  
|<span data-ttu-id="5f0ef-369">COLUMN_FLAGS</span><span class="sxs-lookup"><span data-stu-id="5f0ef-369">COLUMN_FLAGS</span></span>|<span data-ttu-id="5f0ef-370">Int64</span><span class="sxs-lookup"><span data-stu-id="5f0ef-370">Int64</span></span>|  
|<span data-ttu-id="5f0ef-371">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="5f0ef-371">IS_NULLABLE</span></span>|<span data-ttu-id="5f0ef-372">Boolean</span><span class="sxs-lookup"><span data-stu-id="5f0ef-372">Boolean</span></span>|  
|<span data-ttu-id="5f0ef-373">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="5f0ef-373">DATA_TYPE</span></span>|<span data-ttu-id="5f0ef-374">Int32</span><span class="sxs-lookup"><span data-stu-id="5f0ef-374">Int32</span></span>|  
|<span data-ttu-id="5f0ef-375">TYPE_GUID</span><span class="sxs-lookup"><span data-stu-id="5f0ef-375">TYPE_GUID</span></span>|<span data-ttu-id="5f0ef-376">Guid</span><span class="sxs-lookup"><span data-stu-id="5f0ef-376">Guid</span></span>|  
|<span data-ttu-id="5f0ef-377">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="5f0ef-377">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="5f0ef-378">Int64</span><span class="sxs-lookup"><span data-stu-id="5f0ef-378">Int64</span></span>|  
|<span data-ttu-id="5f0ef-379">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="5f0ef-379">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="5f0ef-380">Int64</span><span class="sxs-lookup"><span data-stu-id="5f0ef-380">Int64</span></span>|  
|<span data-ttu-id="5f0ef-381">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="5f0ef-381">NUMERIC_PRECISION</span></span>|<span data-ttu-id="5f0ef-382">Int32</span><span class="sxs-lookup"><span data-stu-id="5f0ef-382">Int32</span></span>|  
|<span data-ttu-id="5f0ef-383">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="5f0ef-383">NUMERIC_SCALE</span></span>|<span data-ttu-id="5f0ef-384">Int16</span><span class="sxs-lookup"><span data-stu-id="5f0ef-384">Int16</span></span>|  
|<span data-ttu-id="5f0ef-385">DATETIME_PRECISION</span><span class="sxs-lookup"><span data-stu-id="5f0ef-385">DATETIME_PRECISION</span></span>|<span data-ttu-id="5f0ef-386">Int64</span><span class="sxs-lookup"><span data-stu-id="5f0ef-386">Int64</span></span>|  
|<span data-ttu-id="5f0ef-387">CHARACTER_SET_CATALOG</span><span class="sxs-lookup"><span data-stu-id="5f0ef-387">CHARACTER_SET_CATALOG</span></span>|<span data-ttu-id="5f0ef-388">Строковое</span><span class="sxs-lookup"><span data-stu-id="5f0ef-388">String</span></span>|  
|<span data-ttu-id="5f0ef-389">CHARACTER_SET_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="5f0ef-389">CHARACTER_SET_SCHEMA</span></span>|<span data-ttu-id="5f0ef-390">Строковое</span><span class="sxs-lookup"><span data-stu-id="5f0ef-390">String</span></span>|  
|<span data-ttu-id="5f0ef-391">CHARACTER_SET_NAME</span><span class="sxs-lookup"><span data-stu-id="5f0ef-391">CHARACTER_SET_NAME</span></span>|<span data-ttu-id="5f0ef-392">Строковое</span><span class="sxs-lookup"><span data-stu-id="5f0ef-392">String</span></span>|  
|<span data-ttu-id="5f0ef-393">COLLATION_CATALOG</span><span class="sxs-lookup"><span data-stu-id="5f0ef-393">COLLATION_CATALOG</span></span>|<span data-ttu-id="5f0ef-394">Строковое</span><span class="sxs-lookup"><span data-stu-id="5f0ef-394">String</span></span>|  
|<span data-ttu-id="5f0ef-395">COLLATION_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="5f0ef-395">COLLATION_SCHEMA</span></span>|<span data-ttu-id="5f0ef-396">Строковое</span><span class="sxs-lookup"><span data-stu-id="5f0ef-396">String</span></span>|  
|<span data-ttu-id="5f0ef-397">COLLATION_NAME</span><span class="sxs-lookup"><span data-stu-id="5f0ef-397">COLLATION_NAME</span></span>|<span data-ttu-id="5f0ef-398">Строковое</span><span class="sxs-lookup"><span data-stu-id="5f0ef-398">String</span></span>|  
|<span data-ttu-id="5f0ef-399">DOMAIN_CATALOG</span><span class="sxs-lookup"><span data-stu-id="5f0ef-399">DOMAIN_CATALOG</span></span>|<span data-ttu-id="5f0ef-400">Строковое</span><span class="sxs-lookup"><span data-stu-id="5f0ef-400">String</span></span>|  
|<span data-ttu-id="5f0ef-401">DOMAIN_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="5f0ef-401">DOMAIN_SCHEMA</span></span>|<span data-ttu-id="5f0ef-402">Строковое</span><span class="sxs-lookup"><span data-stu-id="5f0ef-402">String</span></span>|  
|<span data-ttu-id="5f0ef-403">DOMAIN_NAME</span><span class="sxs-lookup"><span data-stu-id="5f0ef-403">DOMAIN_NAME</span></span>|<span data-ttu-id="5f0ef-404">Строковое</span><span class="sxs-lookup"><span data-stu-id="5f0ef-404">String</span></span>|  
|<span data-ttu-id="5f0ef-405">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="5f0ef-405">DESCRIPTION</span></span>|<span data-ttu-id="5f0ef-406">Строковое</span><span class="sxs-lookup"><span data-stu-id="5f0ef-406">String</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="5f0ef-407">Процедуры</span><span class="sxs-lookup"><span data-stu-id="5f0ef-407">Procedures</span></span>  
  
|<span data-ttu-id="5f0ef-408">ColumnName</span><span class="sxs-lookup"><span data-stu-id="5f0ef-408">ColumnName</span></span>|<span data-ttu-id="5f0ef-409">DataType</span><span class="sxs-lookup"><span data-stu-id="5f0ef-409">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="5f0ef-410">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="5f0ef-410">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="5f0ef-411">Строковое</span><span class="sxs-lookup"><span data-stu-id="5f0ef-411">String</span></span>|  
|<span data-ttu-id="5f0ef-412">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="5f0ef-412">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="5f0ef-413">Строковое</span><span class="sxs-lookup"><span data-stu-id="5f0ef-413">String</span></span>|  
|<span data-ttu-id="5f0ef-414">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="5f0ef-414">PROCEDURE_NAME</span></span>|<span data-ttu-id="5f0ef-415">Строковое</span><span class="sxs-lookup"><span data-stu-id="5f0ef-415">String</span></span>|  
|<span data-ttu-id="5f0ef-416">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="5f0ef-416">PROCEDURE_TYPE</span></span>|<span data-ttu-id="5f0ef-417">Int16</span><span class="sxs-lookup"><span data-stu-id="5f0ef-417">Int16</span></span>|  
|<span data-ttu-id="5f0ef-418">PROCEDURE_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="5f0ef-418">PROCEDURE_DEFINITION</span></span>|<span data-ttu-id="5f0ef-419">Строковое</span><span class="sxs-lookup"><span data-stu-id="5f0ef-419">String</span></span>|  
|<span data-ttu-id="5f0ef-420">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="5f0ef-420">DESCRIPTION</span></span>|<span data-ttu-id="5f0ef-421">Строковое</span><span class="sxs-lookup"><span data-stu-id="5f0ef-421">String</span></span>|  
|<span data-ttu-id="5f0ef-422">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="5f0ef-422">DATE_CREATED</span></span>|<span data-ttu-id="5f0ef-423">DateTime</span><span class="sxs-lookup"><span data-stu-id="5f0ef-423">DateTime</span></span>|  
|<span data-ttu-id="5f0ef-424">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="5f0ef-424">DATE_MODIFIED</span></span>|<span data-ttu-id="5f0ef-425">DateTime</span><span class="sxs-lookup"><span data-stu-id="5f0ef-425">DateTime</span></span>|  
  
### <a name="procedurecolumns"></a><span data-ttu-id="5f0ef-426">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="5f0ef-426">ProcedureColumns</span></span>  
  
|<span data-ttu-id="5f0ef-427">ColumnName</span><span class="sxs-lookup"><span data-stu-id="5f0ef-427">ColumnName</span></span>|<span data-ttu-id="5f0ef-428">DataType</span><span class="sxs-lookup"><span data-stu-id="5f0ef-428">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="5f0ef-429">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="5f0ef-429">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="5f0ef-430">Строковое</span><span class="sxs-lookup"><span data-stu-id="5f0ef-430">String</span></span>|  
|<span data-ttu-id="5f0ef-431">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="5f0ef-431">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="5f0ef-432">Строковое</span><span class="sxs-lookup"><span data-stu-id="5f0ef-432">String</span></span>|  
|<span data-ttu-id="5f0ef-433">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="5f0ef-433">PROCEDURE_NAME</span></span>|<span data-ttu-id="5f0ef-434">Строковое</span><span class="sxs-lookup"><span data-stu-id="5f0ef-434">String</span></span>|  
|<span data-ttu-id="5f0ef-435">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="5f0ef-435">COLUMN_NAME</span></span>|<span data-ttu-id="5f0ef-436">Строковое</span><span class="sxs-lookup"><span data-stu-id="5f0ef-436">String</span></span>|  
|<span data-ttu-id="5f0ef-437">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="5f0ef-437">COLUMN_GUID</span></span>|<span data-ttu-id="5f0ef-438">Guid</span><span class="sxs-lookup"><span data-stu-id="5f0ef-438">Guid</span></span>|  
|<span data-ttu-id="5f0ef-439">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="5f0ef-439">COLUMN_PROPID</span></span>|<span data-ttu-id="5f0ef-440">Int64</span><span class="sxs-lookup"><span data-stu-id="5f0ef-440">Int64</span></span>|  
|<span data-ttu-id="5f0ef-441">ROWSET_NUMBER</span><span class="sxs-lookup"><span data-stu-id="5f0ef-441">ROWSET_NUMBER</span></span>|<span data-ttu-id="5f0ef-442">Int64</span><span class="sxs-lookup"><span data-stu-id="5f0ef-442">Int64</span></span>|  
|<span data-ttu-id="5f0ef-443">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="5f0ef-443">ORDINAL_POSITION</span></span>|<span data-ttu-id="5f0ef-444">Int64</span><span class="sxs-lookup"><span data-stu-id="5f0ef-444">Int64</span></span>|  
|<span data-ttu-id="5f0ef-445">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="5f0ef-445">IS_NULLABLE</span></span>|<span data-ttu-id="5f0ef-446">Boolean</span><span class="sxs-lookup"><span data-stu-id="5f0ef-446">Boolean</span></span>|  
|<span data-ttu-id="5f0ef-447">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="5f0ef-447">DATA_TYPE</span></span>|<span data-ttu-id="5f0ef-448">Int32</span><span class="sxs-lookup"><span data-stu-id="5f0ef-448">Int32</span></span>|  
|<span data-ttu-id="5f0ef-449">TYPE_GUID</span><span class="sxs-lookup"><span data-stu-id="5f0ef-449">TYPE_GUID</span></span>|<span data-ttu-id="5f0ef-450">Guid</span><span class="sxs-lookup"><span data-stu-id="5f0ef-450">Guid</span></span>|  
|<span data-ttu-id="5f0ef-451">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="5f0ef-451">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="5f0ef-452">Int64</span><span class="sxs-lookup"><span data-stu-id="5f0ef-452">Int64</span></span>|  
|<span data-ttu-id="5f0ef-453">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="5f0ef-453">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="5f0ef-454">Int64</span><span class="sxs-lookup"><span data-stu-id="5f0ef-454">Int64</span></span>|  
|<span data-ttu-id="5f0ef-455">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="5f0ef-455">NUMERIC_PRECISION</span></span>|<span data-ttu-id="5f0ef-456">Int32</span><span class="sxs-lookup"><span data-stu-id="5f0ef-456">Int32</span></span>|  
|<span data-ttu-id="5f0ef-457">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="5f0ef-457">NUMERIC_SCALE</span></span>|<span data-ttu-id="5f0ef-458">Int16</span><span class="sxs-lookup"><span data-stu-id="5f0ef-458">Int16</span></span>|  
|<span data-ttu-id="5f0ef-459">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="5f0ef-459">DESCRIPTION</span></span>|<span data-ttu-id="5f0ef-460">Строковое</span><span class="sxs-lookup"><span data-stu-id="5f0ef-460">String</span></span>|  
|<span data-ttu-id="5f0ef-461">OVERLOAD</span><span class="sxs-lookup"><span data-stu-id="5f0ef-461">OVERLOAD</span></span>|<span data-ttu-id="5f0ef-462">Int16</span><span class="sxs-lookup"><span data-stu-id="5f0ef-462">Int16</span></span>|  
  
### <a name="views"></a><span data-ttu-id="5f0ef-463">Представления</span><span class="sxs-lookup"><span data-stu-id="5f0ef-463">Views</span></span>  
  
|<span data-ttu-id="5f0ef-464">ColumnName</span><span class="sxs-lookup"><span data-stu-id="5f0ef-464">ColumnName</span></span>|<span data-ttu-id="5f0ef-465">DataType</span><span class="sxs-lookup"><span data-stu-id="5f0ef-465">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="5f0ef-466">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="5f0ef-466">TABLE_CATALOG</span></span>|<span data-ttu-id="5f0ef-467">Строковое</span><span class="sxs-lookup"><span data-stu-id="5f0ef-467">String</span></span>|  
|<span data-ttu-id="5f0ef-468">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="5f0ef-468">TABLE_SCHEMA</span></span>|<span data-ttu-id="5f0ef-469">Строковое</span><span class="sxs-lookup"><span data-stu-id="5f0ef-469">String</span></span>|  
|<span data-ttu-id="5f0ef-470">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="5f0ef-470">TABLE_NAME</span></span>|<span data-ttu-id="5f0ef-471">Строковое</span><span class="sxs-lookup"><span data-stu-id="5f0ef-471">String</span></span>|  
|<span data-ttu-id="5f0ef-472">VIEW_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="5f0ef-472">VIEW_DEFINITION</span></span>|<span data-ttu-id="5f0ef-473">Строковое</span><span class="sxs-lookup"><span data-stu-id="5f0ef-473">String</span></span>|  
|<span data-ttu-id="5f0ef-474">CHECK_OPTION</span><span class="sxs-lookup"><span data-stu-id="5f0ef-474">CHECK_OPTION</span></span>|<span data-ttu-id="5f0ef-475">Boolean</span><span class="sxs-lookup"><span data-stu-id="5f0ef-475">Boolean</span></span>|  
|<span data-ttu-id="5f0ef-476">IS_UPDATABLE</span><span class="sxs-lookup"><span data-stu-id="5f0ef-476">IS_UPDATABLE</span></span>|<span data-ttu-id="5f0ef-477">Boolean</span><span class="sxs-lookup"><span data-stu-id="5f0ef-477">Boolean</span></span>|  
|<span data-ttu-id="5f0ef-478">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="5f0ef-478">DESCRIPTION</span></span>|<span data-ttu-id="5f0ef-479">Строковое</span><span class="sxs-lookup"><span data-stu-id="5f0ef-479">String</span></span>|  
|<span data-ttu-id="5f0ef-480">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="5f0ef-480">DATE_CREATED</span></span>|<span data-ttu-id="5f0ef-481">DateTime</span><span class="sxs-lookup"><span data-stu-id="5f0ef-481">DateTime</span></span>|  
|<span data-ttu-id="5f0ef-482">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="5f0ef-482">DATE_MODIFIED</span></span>|<span data-ttu-id="5f0ef-483">DateTime</span><span class="sxs-lookup"><span data-stu-id="5f0ef-483">DateTime</span></span>|  
  
### <a name="indexes"></a><span data-ttu-id="5f0ef-484">Indexes</span><span class="sxs-lookup"><span data-stu-id="5f0ef-484">Indexes</span></span>  
  
|<span data-ttu-id="5f0ef-485">ColumnName</span><span class="sxs-lookup"><span data-stu-id="5f0ef-485">ColumnName</span></span>|<span data-ttu-id="5f0ef-486">DataType</span><span class="sxs-lookup"><span data-stu-id="5f0ef-486">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="5f0ef-487">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="5f0ef-487">TABLE_CATALOG</span></span>|<span data-ttu-id="5f0ef-488">Строковое</span><span class="sxs-lookup"><span data-stu-id="5f0ef-488">String</span></span>|  
|<span data-ttu-id="5f0ef-489">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="5f0ef-489">TABLE_SCHEMA</span></span>|<span data-ttu-id="5f0ef-490">Строковое</span><span class="sxs-lookup"><span data-stu-id="5f0ef-490">String</span></span>|  
|<span data-ttu-id="5f0ef-491">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="5f0ef-491">TABLE_NAME</span></span>|<span data-ttu-id="5f0ef-492">Строковое</span><span class="sxs-lookup"><span data-stu-id="5f0ef-492">String</span></span>|  
|<span data-ttu-id="5f0ef-493">INDEX_CATALOG</span><span class="sxs-lookup"><span data-stu-id="5f0ef-493">INDEX_CATALOG</span></span>|<span data-ttu-id="5f0ef-494">Строковое</span><span class="sxs-lookup"><span data-stu-id="5f0ef-494">String</span></span>|  
|<span data-ttu-id="5f0ef-495">INDEX_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="5f0ef-495">INDEX_SCHEMA</span></span>|<span data-ttu-id="5f0ef-496">Строковое</span><span class="sxs-lookup"><span data-stu-id="5f0ef-496">String</span></span>|  
|<span data-ttu-id="5f0ef-497">INDEX_NAME</span><span class="sxs-lookup"><span data-stu-id="5f0ef-497">INDEX_NAME</span></span>|<span data-ttu-id="5f0ef-498">Строковое</span><span class="sxs-lookup"><span data-stu-id="5f0ef-498">String</span></span>|  
|<span data-ttu-id="5f0ef-499">PRIMARY_KEY</span><span class="sxs-lookup"><span data-stu-id="5f0ef-499">PRIMARY_KEY</span></span>|<span data-ttu-id="5f0ef-500">Boolean</span><span class="sxs-lookup"><span data-stu-id="5f0ef-500">Boolean</span></span>|  
|<span data-ttu-id="5f0ef-501">UNIQUE</span><span class="sxs-lookup"><span data-stu-id="5f0ef-501">UNIQUE</span></span>|<span data-ttu-id="5f0ef-502">Boolean</span><span class="sxs-lookup"><span data-stu-id="5f0ef-502">Boolean</span></span>|  
|<span data-ttu-id="5f0ef-503">CLUSTERED</span><span class="sxs-lookup"><span data-stu-id="5f0ef-503">CLUSTERED</span></span>|<span data-ttu-id="5f0ef-504">Boolean</span><span class="sxs-lookup"><span data-stu-id="5f0ef-504">Boolean</span></span>|  
|<span data-ttu-id="5f0ef-505">TYPE</span><span class="sxs-lookup"><span data-stu-id="5f0ef-505">TYPE</span></span>|<span data-ttu-id="5f0ef-506">Int32</span><span class="sxs-lookup"><span data-stu-id="5f0ef-506">Int32</span></span>|  
|<span data-ttu-id="5f0ef-507">FILL_FACTOR</span><span class="sxs-lookup"><span data-stu-id="5f0ef-507">FILL_FACTOR</span></span>|<span data-ttu-id="5f0ef-508">Int32</span><span class="sxs-lookup"><span data-stu-id="5f0ef-508">Int32</span></span>|  
|<span data-ttu-id="5f0ef-509">INITIAL_SIZE</span><span class="sxs-lookup"><span data-stu-id="5f0ef-509">INITIAL_SIZE</span></span>|<span data-ttu-id="5f0ef-510">Int32</span><span class="sxs-lookup"><span data-stu-id="5f0ef-510">Int32</span></span>|  
|<span data-ttu-id="5f0ef-511">NULLS</span><span class="sxs-lookup"><span data-stu-id="5f0ef-511">NULLS</span></span>|<span data-ttu-id="5f0ef-512">Int32</span><span class="sxs-lookup"><span data-stu-id="5f0ef-512">Int32</span></span>|  
|<span data-ttu-id="5f0ef-513">SORT_BOOKMARKS</span><span class="sxs-lookup"><span data-stu-id="5f0ef-513">SORT_BOOKMARKS</span></span>|<span data-ttu-id="5f0ef-514">Boolean</span><span class="sxs-lookup"><span data-stu-id="5f0ef-514">Boolean</span></span>|  
|<span data-ttu-id="5f0ef-515">AUTO_UPDATE</span><span class="sxs-lookup"><span data-stu-id="5f0ef-515">AUTO_UPDATE</span></span>|<span data-ttu-id="5f0ef-516">Boolean</span><span class="sxs-lookup"><span data-stu-id="5f0ef-516">Boolean</span></span>|  
|<span data-ttu-id="5f0ef-517">NULL_COLLATION</span><span class="sxs-lookup"><span data-stu-id="5f0ef-517">NULL_COLLATION</span></span>|<span data-ttu-id="5f0ef-518">Int32</span><span class="sxs-lookup"><span data-stu-id="5f0ef-518">Int32</span></span>|  
|<span data-ttu-id="5f0ef-519">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="5f0ef-519">ORDINAL_POSITION</span></span>|<span data-ttu-id="5f0ef-520">Int64</span><span class="sxs-lookup"><span data-stu-id="5f0ef-520">Int64</span></span>|  
|<span data-ttu-id="5f0ef-521">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="5f0ef-521">COLUMN_NAME</span></span>|<span data-ttu-id="5f0ef-522">Строковое</span><span class="sxs-lookup"><span data-stu-id="5f0ef-522">String</span></span>|  
|<span data-ttu-id="5f0ef-523">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="5f0ef-523">COLUMN_GUID</span></span>|<span data-ttu-id="5f0ef-524">Guid</span><span class="sxs-lookup"><span data-stu-id="5f0ef-524">Guid</span></span>|  
|<span data-ttu-id="5f0ef-525">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="5f0ef-525">COLUMN_PROPID</span></span>|<span data-ttu-id="5f0ef-526">Int64</span><span class="sxs-lookup"><span data-stu-id="5f0ef-526">Int64</span></span>|  
|<span data-ttu-id="5f0ef-527">COLLATION</span><span class="sxs-lookup"><span data-stu-id="5f0ef-527">COLLATION</span></span>|<span data-ttu-id="5f0ef-528">Int16</span><span class="sxs-lookup"><span data-stu-id="5f0ef-528">Int16</span></span>|  
|<span data-ttu-id="5f0ef-529">CARDINALITY</span><span class="sxs-lookup"><span data-stu-id="5f0ef-529">CARDINALITY</span></span>|<span data-ttu-id="5f0ef-530">Десятичное число</span><span class="sxs-lookup"><span data-stu-id="5f0ef-530">Decimal</span></span>|  
|<span data-ttu-id="5f0ef-531">PAGES</span><span class="sxs-lookup"><span data-stu-id="5f0ef-531">PAGES</span></span>|<span data-ttu-id="5f0ef-532">Int32</span><span class="sxs-lookup"><span data-stu-id="5f0ef-532">Int32</span></span>|  
|<span data-ttu-id="5f0ef-533">FILTER_CONDITION</span><span class="sxs-lookup"><span data-stu-id="5f0ef-533">FILTER_CONDITION</span></span>|<span data-ttu-id="5f0ef-534">Строковое</span><span class="sxs-lookup"><span data-stu-id="5f0ef-534">String</span></span>|  
|<span data-ttu-id="5f0ef-535">INTEGRATED</span><span class="sxs-lookup"><span data-stu-id="5f0ef-535">INTEGRATED</span></span>|<span data-ttu-id="5f0ef-536">Boolean</span><span class="sxs-lookup"><span data-stu-id="5f0ef-536">Boolean</span></span>|  
  
## <a name="microsoft-jet-ole-db-provider"></a><span data-ttu-id="5f0ef-537">Поставщик OLE DB для Microsoft Jet</span><span class="sxs-lookup"><span data-stu-id="5f0ef-537">Microsoft Jet OLE DB Provider</span></span>  
 <span data-ttu-id="5f0ef-538">Драйвер OLE DB для Jet (Майкрософт) поддерживает следующие специальные коллекции схем в дополнение к общим коллекциям.</span><span class="sxs-lookup"><span data-stu-id="5f0ef-538">The Microsoft Jet OLE DB Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
-   <span data-ttu-id="5f0ef-539">Таблицы</span><span class="sxs-lookup"><span data-stu-id="5f0ef-539">Tables</span></span>  
  
-   <span data-ttu-id="5f0ef-540">Столбцы</span><span class="sxs-lookup"><span data-stu-id="5f0ef-540">Columns</span></span>  
  
-   <span data-ttu-id="5f0ef-541">Процедуры</span><span class="sxs-lookup"><span data-stu-id="5f0ef-541">Procedures</span></span>  
  
-   <span data-ttu-id="5f0ef-542">Представления</span><span class="sxs-lookup"><span data-stu-id="5f0ef-542">Views</span></span>  
  
-   <span data-ttu-id="5f0ef-543">Indexes</span><span class="sxs-lookup"><span data-stu-id="5f0ef-543">Indexes</span></span>  
  
### <a name="tables"></a><span data-ttu-id="5f0ef-544">Таблицы</span><span class="sxs-lookup"><span data-stu-id="5f0ef-544">Tables</span></span>  
  
|<span data-ttu-id="5f0ef-545">ColumnName</span><span class="sxs-lookup"><span data-stu-id="5f0ef-545">ColumnName</span></span>|<span data-ttu-id="5f0ef-546">DataType</span><span class="sxs-lookup"><span data-stu-id="5f0ef-546">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="5f0ef-547">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="5f0ef-547">TABLE_CATALOG</span></span>|<span data-ttu-id="5f0ef-548">Строковое</span><span class="sxs-lookup"><span data-stu-id="5f0ef-548">String</span></span>|  
|<span data-ttu-id="5f0ef-549">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="5f0ef-549">TABLE_SCHEMA</span></span>|<span data-ttu-id="5f0ef-550">Строковое</span><span class="sxs-lookup"><span data-stu-id="5f0ef-550">String</span></span>|  
|<span data-ttu-id="5f0ef-551">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="5f0ef-551">TABLE_NAME</span></span>|<span data-ttu-id="5f0ef-552">Строковое</span><span class="sxs-lookup"><span data-stu-id="5f0ef-552">String</span></span>|  
|<span data-ttu-id="5f0ef-553">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="5f0ef-553">TABLE_TYPE</span></span>|<span data-ttu-id="5f0ef-554">Строковое</span><span class="sxs-lookup"><span data-stu-id="5f0ef-554">String</span></span>|  
|<span data-ttu-id="5f0ef-555">TABLE_GUID</span><span class="sxs-lookup"><span data-stu-id="5f0ef-555">TABLE_GUID</span></span>|<span data-ttu-id="5f0ef-556">Guid</span><span class="sxs-lookup"><span data-stu-id="5f0ef-556">Guid</span></span>|  
|<span data-ttu-id="5f0ef-557">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="5f0ef-557">DESCRIPTION</span></span>|<span data-ttu-id="5f0ef-558">Строковое</span><span class="sxs-lookup"><span data-stu-id="5f0ef-558">String</span></span>|  
|<span data-ttu-id="5f0ef-559">TABLE_PROPID</span><span class="sxs-lookup"><span data-stu-id="5f0ef-559">TABLE_PROPID</span></span>|<span data-ttu-id="5f0ef-560">Int64</span><span class="sxs-lookup"><span data-stu-id="5f0ef-560">Int64</span></span>|  
|<span data-ttu-id="5f0ef-561">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="5f0ef-561">DATE_CREATED</span></span>|<span data-ttu-id="5f0ef-562">DateTime</span><span class="sxs-lookup"><span data-stu-id="5f0ef-562">DateTime</span></span>|  
|<span data-ttu-id="5f0ef-563">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="5f0ef-563">DATE_MODIFIED</span></span>|<span data-ttu-id="5f0ef-564">DateTime</span><span class="sxs-lookup"><span data-stu-id="5f0ef-564">DateTime</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="5f0ef-565">Столбцы</span><span class="sxs-lookup"><span data-stu-id="5f0ef-565">Columns</span></span>  
  
|<span data-ttu-id="5f0ef-566">ColumnName</span><span class="sxs-lookup"><span data-stu-id="5f0ef-566">ColumnName</span></span>|<span data-ttu-id="5f0ef-567">DataType</span><span class="sxs-lookup"><span data-stu-id="5f0ef-567">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="5f0ef-568">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="5f0ef-568">TABLE_CATALOG</span></span>|<span data-ttu-id="5f0ef-569">Строковое</span><span class="sxs-lookup"><span data-stu-id="5f0ef-569">String</span></span>|  
|<span data-ttu-id="5f0ef-570">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="5f0ef-570">TABLE_SCHEMA</span></span>|<span data-ttu-id="5f0ef-571">Строковое</span><span class="sxs-lookup"><span data-stu-id="5f0ef-571">String</span></span>|  
|<span data-ttu-id="5f0ef-572">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="5f0ef-572">TABLE_NAME</span></span>|<span data-ttu-id="5f0ef-573">Строковое</span><span class="sxs-lookup"><span data-stu-id="5f0ef-573">String</span></span>|  
|<span data-ttu-id="5f0ef-574">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="5f0ef-574">COLUMN_NAME</span></span>|<span data-ttu-id="5f0ef-575">Строковое</span><span class="sxs-lookup"><span data-stu-id="5f0ef-575">String</span></span>|  
|<span data-ttu-id="5f0ef-576">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="5f0ef-576">COLUMN_GUID</span></span>|<span data-ttu-id="5f0ef-577">Guid</span><span class="sxs-lookup"><span data-stu-id="5f0ef-577">Guid</span></span>|  
|<span data-ttu-id="5f0ef-578">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="5f0ef-578">COLUMN_PROPID</span></span>|<span data-ttu-id="5f0ef-579">Int64</span><span class="sxs-lookup"><span data-stu-id="5f0ef-579">Int64</span></span>|  
|<span data-ttu-id="5f0ef-580">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="5f0ef-580">ORDINAL_POSITION</span></span>|<span data-ttu-id="5f0ef-581">Int64</span><span class="sxs-lookup"><span data-stu-id="5f0ef-581">Int64</span></span>|  
|<span data-ttu-id="5f0ef-582">COLUMN_HASDEFAULT</span><span class="sxs-lookup"><span data-stu-id="5f0ef-582">COLUMN_HASDEFAULT</span></span>|<span data-ttu-id="5f0ef-583">Boolean</span><span class="sxs-lookup"><span data-stu-id="5f0ef-583">Boolean</span></span>|  
|<span data-ttu-id="5f0ef-584">COLUMN_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="5f0ef-584">COLUMN_DEFAULT</span></span>|<span data-ttu-id="5f0ef-585">Строковое</span><span class="sxs-lookup"><span data-stu-id="5f0ef-585">String</span></span>|  
|<span data-ttu-id="5f0ef-586">COLUMN_FLAGS</span><span class="sxs-lookup"><span data-stu-id="5f0ef-586">COLUMN_FLAGS</span></span>|<span data-ttu-id="5f0ef-587">Int64</span><span class="sxs-lookup"><span data-stu-id="5f0ef-587">Int64</span></span>|  
|<span data-ttu-id="5f0ef-588">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="5f0ef-588">IS_NULLABLE</span></span>|<span data-ttu-id="5f0ef-589">Boolean</span><span class="sxs-lookup"><span data-stu-id="5f0ef-589">Boolean</span></span>|  
|<span data-ttu-id="5f0ef-590">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="5f0ef-590">DATA_TYPE</span></span>|<span data-ttu-id="5f0ef-591">Int32</span><span class="sxs-lookup"><span data-stu-id="5f0ef-591">Int32</span></span>|  
|<span data-ttu-id="5f0ef-592">TYPE_GUID</span><span class="sxs-lookup"><span data-stu-id="5f0ef-592">TYPE_GUID</span></span>|<span data-ttu-id="5f0ef-593">Guid</span><span class="sxs-lookup"><span data-stu-id="5f0ef-593">Guid</span></span>|  
|<span data-ttu-id="5f0ef-594">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="5f0ef-594">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="5f0ef-595">Int64</span><span class="sxs-lookup"><span data-stu-id="5f0ef-595">Int64</span></span>|  
|<span data-ttu-id="5f0ef-596">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="5f0ef-596">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="5f0ef-597">Int64</span><span class="sxs-lookup"><span data-stu-id="5f0ef-597">Int64</span></span>|  
|<span data-ttu-id="5f0ef-598">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="5f0ef-598">NUMERIC_PRECISION</span></span>|<span data-ttu-id="5f0ef-599">Int32</span><span class="sxs-lookup"><span data-stu-id="5f0ef-599">Int32</span></span>|  
|<span data-ttu-id="5f0ef-600">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="5f0ef-600">NUMERIC_SCALE</span></span>|<span data-ttu-id="5f0ef-601">Int16</span><span class="sxs-lookup"><span data-stu-id="5f0ef-601">Int16</span></span>|  
|<span data-ttu-id="5f0ef-602">DATETIME_PRECISION</span><span class="sxs-lookup"><span data-stu-id="5f0ef-602">DATETIME_PRECISION</span></span>|<span data-ttu-id="5f0ef-603">Int64</span><span class="sxs-lookup"><span data-stu-id="5f0ef-603">Int64</span></span>|  
|<span data-ttu-id="5f0ef-604">CHARACTER_SET_CATALOG</span><span class="sxs-lookup"><span data-stu-id="5f0ef-604">CHARACTER_SET_CATALOG</span></span>|<span data-ttu-id="5f0ef-605">Строковое</span><span class="sxs-lookup"><span data-stu-id="5f0ef-605">String</span></span>|  
|<span data-ttu-id="5f0ef-606">CHARACTER_SET_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="5f0ef-606">CHARACTER_SET_SCHEMA</span></span>|<span data-ttu-id="5f0ef-607">Строковое</span><span class="sxs-lookup"><span data-stu-id="5f0ef-607">String</span></span>|  
|<span data-ttu-id="5f0ef-608">CHARACTER_SET_NAME</span><span class="sxs-lookup"><span data-stu-id="5f0ef-608">CHARACTER_SET_NAME</span></span>|<span data-ttu-id="5f0ef-609">Строковое</span><span class="sxs-lookup"><span data-stu-id="5f0ef-609">String</span></span>|  
|<span data-ttu-id="5f0ef-610">COLLATION_CATALOG</span><span class="sxs-lookup"><span data-stu-id="5f0ef-610">COLLATION_CATALOG</span></span>|<span data-ttu-id="5f0ef-611">Строковое</span><span class="sxs-lookup"><span data-stu-id="5f0ef-611">String</span></span>|  
|<span data-ttu-id="5f0ef-612">COLLATION_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="5f0ef-612">COLLATION_SCHEMA</span></span>|<span data-ttu-id="5f0ef-613">Строковое</span><span class="sxs-lookup"><span data-stu-id="5f0ef-613">String</span></span>|  
|<span data-ttu-id="5f0ef-614">COLLATION_NAME</span><span class="sxs-lookup"><span data-stu-id="5f0ef-614">COLLATION_NAME</span></span>|<span data-ttu-id="5f0ef-615">Строковое</span><span class="sxs-lookup"><span data-stu-id="5f0ef-615">String</span></span>|  
|<span data-ttu-id="5f0ef-616">DOMAIN_CATALOG</span><span class="sxs-lookup"><span data-stu-id="5f0ef-616">DOMAIN_CATALOG</span></span>|<span data-ttu-id="5f0ef-617">Строковое</span><span class="sxs-lookup"><span data-stu-id="5f0ef-617">String</span></span>|  
|<span data-ttu-id="5f0ef-618">DOMAIN_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="5f0ef-618">DOMAIN_SCHEMA</span></span>|<span data-ttu-id="5f0ef-619">Строковое</span><span class="sxs-lookup"><span data-stu-id="5f0ef-619">String</span></span>|  
|<span data-ttu-id="5f0ef-620">DOMAIN_NAME</span><span class="sxs-lookup"><span data-stu-id="5f0ef-620">DOMAIN_NAME</span></span>|<span data-ttu-id="5f0ef-621">Строковое</span><span class="sxs-lookup"><span data-stu-id="5f0ef-621">String</span></span>|  
|<span data-ttu-id="5f0ef-622">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="5f0ef-622">DESCRIPTION</span></span>|<span data-ttu-id="5f0ef-623">Строковое</span><span class="sxs-lookup"><span data-stu-id="5f0ef-623">String</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="5f0ef-624">Процедуры</span><span class="sxs-lookup"><span data-stu-id="5f0ef-624">Procedures</span></span>  
  
|<span data-ttu-id="5f0ef-625">ColumnName</span><span class="sxs-lookup"><span data-stu-id="5f0ef-625">ColumnName</span></span>|<span data-ttu-id="5f0ef-626">DataType</span><span class="sxs-lookup"><span data-stu-id="5f0ef-626">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="5f0ef-627">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="5f0ef-627">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="5f0ef-628">Строковое</span><span class="sxs-lookup"><span data-stu-id="5f0ef-628">String</span></span>|  
|<span data-ttu-id="5f0ef-629">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="5f0ef-629">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="5f0ef-630">Строковое</span><span class="sxs-lookup"><span data-stu-id="5f0ef-630">String</span></span>|  
|<span data-ttu-id="5f0ef-631">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="5f0ef-631">PROCEDURE_NAME</span></span>|<span data-ttu-id="5f0ef-632">Строковое</span><span class="sxs-lookup"><span data-stu-id="5f0ef-632">String</span></span>|  
|<span data-ttu-id="5f0ef-633">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="5f0ef-633">PROCEDURE_TYPE</span></span>|<span data-ttu-id="5f0ef-634">Int16</span><span class="sxs-lookup"><span data-stu-id="5f0ef-634">Int16</span></span>|  
|<span data-ttu-id="5f0ef-635">PROCEDURE_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="5f0ef-635">PROCEDURE_DEFINITION</span></span>|<span data-ttu-id="5f0ef-636">Строковое</span><span class="sxs-lookup"><span data-stu-id="5f0ef-636">String</span></span>|  
|<span data-ttu-id="5f0ef-637">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="5f0ef-637">DESCRIPTION</span></span>|<span data-ttu-id="5f0ef-638">Строковое</span><span class="sxs-lookup"><span data-stu-id="5f0ef-638">String</span></span>|  
|<span data-ttu-id="5f0ef-639">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="5f0ef-639">DATE_CREATED</span></span>|<span data-ttu-id="5f0ef-640">DateTime</span><span class="sxs-lookup"><span data-stu-id="5f0ef-640">DateTime</span></span>|  
|<span data-ttu-id="5f0ef-641">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="5f0ef-641">DATE_MODIFIED</span></span>|<span data-ttu-id="5f0ef-642">DateTime</span><span class="sxs-lookup"><span data-stu-id="5f0ef-642">DateTime</span></span>|  
  
### <a name="views"></a><span data-ttu-id="5f0ef-643">Представления</span><span class="sxs-lookup"><span data-stu-id="5f0ef-643">Views</span></span>  
  
|<span data-ttu-id="5f0ef-644">ColumnName</span><span class="sxs-lookup"><span data-stu-id="5f0ef-644">ColumnName</span></span>|<span data-ttu-id="5f0ef-645">DataType</span><span class="sxs-lookup"><span data-stu-id="5f0ef-645">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="5f0ef-646">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="5f0ef-646">TABLE_CATALOG</span></span>|<span data-ttu-id="5f0ef-647">Строковое</span><span class="sxs-lookup"><span data-stu-id="5f0ef-647">String</span></span>|  
|<span data-ttu-id="5f0ef-648">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="5f0ef-648">TABLE_SCHEMA</span></span>|<span data-ttu-id="5f0ef-649">Строковое</span><span class="sxs-lookup"><span data-stu-id="5f0ef-649">String</span></span>|  
|<span data-ttu-id="5f0ef-650">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="5f0ef-650">TABLE_NAME</span></span>|<span data-ttu-id="5f0ef-651">Строковое</span><span class="sxs-lookup"><span data-stu-id="5f0ef-651">String</span></span>|  
|<span data-ttu-id="5f0ef-652">VIEW_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="5f0ef-652">VIEW_DEFINITION</span></span>|<span data-ttu-id="5f0ef-653">Строковое</span><span class="sxs-lookup"><span data-stu-id="5f0ef-653">String</span></span>|  
|<span data-ttu-id="5f0ef-654">CHECK_OPTION</span><span class="sxs-lookup"><span data-stu-id="5f0ef-654">CHECK_OPTION</span></span>|<span data-ttu-id="5f0ef-655">Boolean</span><span class="sxs-lookup"><span data-stu-id="5f0ef-655">Boolean</span></span>|  
|<span data-ttu-id="5f0ef-656">IS_UPDATABLE</span><span class="sxs-lookup"><span data-stu-id="5f0ef-656">IS_UPDATABLE</span></span>|<span data-ttu-id="5f0ef-657">Boolean</span><span class="sxs-lookup"><span data-stu-id="5f0ef-657">Boolean</span></span>|  
|<span data-ttu-id="5f0ef-658">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="5f0ef-658">DESCRIPTION</span></span>|<span data-ttu-id="5f0ef-659">Строковое</span><span class="sxs-lookup"><span data-stu-id="5f0ef-659">String</span></span>|  
|<span data-ttu-id="5f0ef-660">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="5f0ef-660">DATE_CREATED</span></span>|<span data-ttu-id="5f0ef-661">DateTime</span><span class="sxs-lookup"><span data-stu-id="5f0ef-661">DateTime</span></span>|  
|<span data-ttu-id="5f0ef-662">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="5f0ef-662">DATE_MODIFIED</span></span>|<span data-ttu-id="5f0ef-663">DateTime</span><span class="sxs-lookup"><span data-stu-id="5f0ef-663">DateTime</span></span>|  
  
### <a name="indexes"></a><span data-ttu-id="5f0ef-664">Indexes</span><span class="sxs-lookup"><span data-stu-id="5f0ef-664">Indexes</span></span>  
  
|<span data-ttu-id="5f0ef-665">ColumnName</span><span class="sxs-lookup"><span data-stu-id="5f0ef-665">ColumnName</span></span>|<span data-ttu-id="5f0ef-666">DataType</span><span class="sxs-lookup"><span data-stu-id="5f0ef-666">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="5f0ef-667">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="5f0ef-667">TABLE_CATALOG</span></span>|<span data-ttu-id="5f0ef-668">Строковое</span><span class="sxs-lookup"><span data-stu-id="5f0ef-668">String</span></span>|  
|<span data-ttu-id="5f0ef-669">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="5f0ef-669">TABLE_SCHEMA</span></span>|<span data-ttu-id="5f0ef-670">Строковое</span><span class="sxs-lookup"><span data-stu-id="5f0ef-670">String</span></span>|  
|<span data-ttu-id="5f0ef-671">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="5f0ef-671">TABLE_NAME</span></span>|<span data-ttu-id="5f0ef-672">Строковое</span><span class="sxs-lookup"><span data-stu-id="5f0ef-672">String</span></span>|  
|<span data-ttu-id="5f0ef-673">INDEX_CATALOG</span><span class="sxs-lookup"><span data-stu-id="5f0ef-673">INDEX_CATALOG</span></span>|<span data-ttu-id="5f0ef-674">Строковое</span><span class="sxs-lookup"><span data-stu-id="5f0ef-674">String</span></span>|  
|<span data-ttu-id="5f0ef-675">INDEX_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="5f0ef-675">INDEX_SCHEMA</span></span>|<span data-ttu-id="5f0ef-676">Строковое</span><span class="sxs-lookup"><span data-stu-id="5f0ef-676">String</span></span>|  
|<span data-ttu-id="5f0ef-677">INDEX_NAME</span><span class="sxs-lookup"><span data-stu-id="5f0ef-677">INDEX_NAME</span></span>|<span data-ttu-id="5f0ef-678">Строковое</span><span class="sxs-lookup"><span data-stu-id="5f0ef-678">String</span></span>|  
|<span data-ttu-id="5f0ef-679">PRIMARY_KEY</span><span class="sxs-lookup"><span data-stu-id="5f0ef-679">PRIMARY_KEY</span></span>|<span data-ttu-id="5f0ef-680">Boolean</span><span class="sxs-lookup"><span data-stu-id="5f0ef-680">Boolean</span></span>|  
|<span data-ttu-id="5f0ef-681">UNIQUE</span><span class="sxs-lookup"><span data-stu-id="5f0ef-681">UNIQUE</span></span>|<span data-ttu-id="5f0ef-682">Boolean</span><span class="sxs-lookup"><span data-stu-id="5f0ef-682">Boolean</span></span>|  
|<span data-ttu-id="5f0ef-683">CLUSTERED</span><span class="sxs-lookup"><span data-stu-id="5f0ef-683">CLUSTERED</span></span>|<span data-ttu-id="5f0ef-684">Boolean</span><span class="sxs-lookup"><span data-stu-id="5f0ef-684">Boolean</span></span>|  
|<span data-ttu-id="5f0ef-685">TYPE</span><span class="sxs-lookup"><span data-stu-id="5f0ef-685">TYPE</span></span>|<span data-ttu-id="5f0ef-686">Int32</span><span class="sxs-lookup"><span data-stu-id="5f0ef-686">Int32</span></span>|  
|<span data-ttu-id="5f0ef-687">FILL_FACTOR</span><span class="sxs-lookup"><span data-stu-id="5f0ef-687">FILL_FACTOR</span></span>|<span data-ttu-id="5f0ef-688">Int32</span><span class="sxs-lookup"><span data-stu-id="5f0ef-688">Int32</span></span>|  
|<span data-ttu-id="5f0ef-689">INITIAL_SIZE</span><span class="sxs-lookup"><span data-stu-id="5f0ef-689">INITIAL_SIZE</span></span>|<span data-ttu-id="5f0ef-690">Int32</span><span class="sxs-lookup"><span data-stu-id="5f0ef-690">Int32</span></span>|  
|<span data-ttu-id="5f0ef-691">NULLS</span><span class="sxs-lookup"><span data-stu-id="5f0ef-691">NULLS</span></span>|<span data-ttu-id="5f0ef-692">Int32</span><span class="sxs-lookup"><span data-stu-id="5f0ef-692">Int32</span></span>|  
|<span data-ttu-id="5f0ef-693">SORT_BOOKMARKS</span><span class="sxs-lookup"><span data-stu-id="5f0ef-693">SORT_BOOKMARKS</span></span>|<span data-ttu-id="5f0ef-694">Boolean</span><span class="sxs-lookup"><span data-stu-id="5f0ef-694">Boolean</span></span>|  
|<span data-ttu-id="5f0ef-695">AUTO_UPDATE</span><span class="sxs-lookup"><span data-stu-id="5f0ef-695">AUTO_UPDATE</span></span>|<span data-ttu-id="5f0ef-696">Boolean</span><span class="sxs-lookup"><span data-stu-id="5f0ef-696">Boolean</span></span>|  
|<span data-ttu-id="5f0ef-697">NULL_COLLATION</span><span class="sxs-lookup"><span data-stu-id="5f0ef-697">NULL_COLLATION</span></span>|<span data-ttu-id="5f0ef-698">Int32</span><span class="sxs-lookup"><span data-stu-id="5f0ef-698">Int32</span></span>|  
|<span data-ttu-id="5f0ef-699">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="5f0ef-699">ORDINAL_POSITION</span></span>|<span data-ttu-id="5f0ef-700">Int64</span><span class="sxs-lookup"><span data-stu-id="5f0ef-700">Int64</span></span>|  
|<span data-ttu-id="5f0ef-701">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="5f0ef-701">COLUMN_NAME</span></span>|<span data-ttu-id="5f0ef-702">Строковое</span><span class="sxs-lookup"><span data-stu-id="5f0ef-702">String</span></span>|  
|<span data-ttu-id="5f0ef-703">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="5f0ef-703">COLUMN_GUID</span></span>|<span data-ttu-id="5f0ef-704">Guid</span><span class="sxs-lookup"><span data-stu-id="5f0ef-704">Guid</span></span>|  
|<span data-ttu-id="5f0ef-705">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="5f0ef-705">COLUMN_PROPID</span></span>|<span data-ttu-id="5f0ef-706">Int64</span><span class="sxs-lookup"><span data-stu-id="5f0ef-706">Int64</span></span>|  
|<span data-ttu-id="5f0ef-707">COLLATION</span><span class="sxs-lookup"><span data-stu-id="5f0ef-707">COLLATION</span></span>|<span data-ttu-id="5f0ef-708">Int16</span><span class="sxs-lookup"><span data-stu-id="5f0ef-708">Int16</span></span>|  
|<span data-ttu-id="5f0ef-709">CARDINALITY</span><span class="sxs-lookup"><span data-stu-id="5f0ef-709">CARDINALITY</span></span>|<span data-ttu-id="5f0ef-710">Десятичное число</span><span class="sxs-lookup"><span data-stu-id="5f0ef-710">Decimal</span></span>|  
|<span data-ttu-id="5f0ef-711">PAGES</span><span class="sxs-lookup"><span data-stu-id="5f0ef-711">PAGES</span></span>|<span data-ttu-id="5f0ef-712">Int32</span><span class="sxs-lookup"><span data-stu-id="5f0ef-712">Int32</span></span>|  
|<span data-ttu-id="5f0ef-713">FILTER_CONDITION</span><span class="sxs-lookup"><span data-stu-id="5f0ef-713">FILTER_CONDITION</span></span>|<span data-ttu-id="5f0ef-714">Строковое</span><span class="sxs-lookup"><span data-stu-id="5f0ef-714">String</span></span>|  
|<span data-ttu-id="5f0ef-715">INTEGRATED</span><span class="sxs-lookup"><span data-stu-id="5f0ef-715">INTEGRATED</span></span>|<span data-ttu-id="5f0ef-716">Boolean</span><span class="sxs-lookup"><span data-stu-id="5f0ef-716">Boolean</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="5f0ef-717">См. также</span><span class="sxs-lookup"><span data-stu-id="5f0ef-717">See Also</span></span>  
 [<span data-ttu-id="5f0ef-718">Центр разработчиков наборов данных и управляемых поставщиков ADO.NET</span><span class="sxs-lookup"><span data-stu-id="5f0ef-718">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
