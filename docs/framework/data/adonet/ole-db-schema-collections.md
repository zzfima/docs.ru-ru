---
title: Коллекции схемы OLE DB
ms.date: 03/30/2017
ms.assetid: 6380c36b-658e-4d67-91e8-7131ef4a7c2c
ms.openlocfilehash: 2d5718c12100ebea49a6b6fab29a3790918c6ad3
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2019
ms.locfileid: "70783452"
---
# <a name="ole-db-schema-collections"></a><span data-ttu-id="7c0dd-102">Коллекции схемы OLE DB</span><span class="sxs-lookup"><span data-stu-id="7c0dd-102">OLE DB Schema Collections</span></span>
<span data-ttu-id="7c0dd-103">В данном разделе рассматривается поддержка коллекций схем для поставщиков OLE DB для Microsoft SQL Server, Oracle и Microsoft Jet.</span><span class="sxs-lookup"><span data-stu-id="7c0dd-103">This section discusses schema collection support for the OLE DB providers for Microsoft SQL Server, Oracle, and Microsoft Jet.</span></span>  
  
## <a name="microsoft-sql-server-ole-db-provider"></a><span data-ttu-id="7c0dd-104">Поставщик OLE DB для Microsoft SQL Server</span><span class="sxs-lookup"><span data-stu-id="7c0dd-104">Microsoft SQL Server OLE DB Provider</span></span>  
 <span data-ttu-id="7c0dd-105">Драйвер Microsoft SQL Server OLE DB поддерживает следующие конкретные коллекции схем в дополнение к общим коллекциям схем:</span><span class="sxs-lookup"><span data-stu-id="7c0dd-105">The Microsoft SQL Server OLE DB Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
- <span data-ttu-id="7c0dd-106">Таблицы</span><span class="sxs-lookup"><span data-stu-id="7c0dd-106">Tables</span></span>  
  
- <span data-ttu-id="7c0dd-107">Столбцы</span><span class="sxs-lookup"><span data-stu-id="7c0dd-107">Columns</span></span>  
  
- <span data-ttu-id="7c0dd-108">Процедуры</span><span class="sxs-lookup"><span data-stu-id="7c0dd-108">Procedures</span></span>  
  
- <span data-ttu-id="7c0dd-109">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="7c0dd-109">ProcedureParameters</span></span>  
  
- <span data-ttu-id="7c0dd-110">Catalog</span><span class="sxs-lookup"><span data-stu-id="7c0dd-110">Catalog</span></span>  
  
- <span data-ttu-id="7c0dd-111">Индексы</span><span class="sxs-lookup"><span data-stu-id="7c0dd-111">Indexes</span></span>  
  
### <a name="tables"></a><span data-ttu-id="7c0dd-112">Таблицы</span><span class="sxs-lookup"><span data-stu-id="7c0dd-112">Tables</span></span>  
  
|<span data-ttu-id="7c0dd-113">ColumnName</span><span class="sxs-lookup"><span data-stu-id="7c0dd-113">ColumnName</span></span>|<span data-ttu-id="7c0dd-114">DataType</span><span class="sxs-lookup"><span data-stu-id="7c0dd-114">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="7c0dd-115">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="7c0dd-115">TABLE_CATALOG</span></span>|<span data-ttu-id="7c0dd-116">String</span><span class="sxs-lookup"><span data-stu-id="7c0dd-116">String</span></span>|  
|<span data-ttu-id="7c0dd-117">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="7c0dd-117">TABLE_SCHEMA</span></span>|<span data-ttu-id="7c0dd-118">String</span><span class="sxs-lookup"><span data-stu-id="7c0dd-118">String</span></span>|  
|<span data-ttu-id="7c0dd-119">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="7c0dd-119">TABLE_NAME</span></span>|<span data-ttu-id="7c0dd-120">String</span><span class="sxs-lookup"><span data-stu-id="7c0dd-120">String</span></span>|  
|<span data-ttu-id="7c0dd-121">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="7c0dd-121">TABLE_TYPE</span></span>|<span data-ttu-id="7c0dd-122">String</span><span class="sxs-lookup"><span data-stu-id="7c0dd-122">String</span></span>|  
|<span data-ttu-id="7c0dd-123">TABLE_GUID</span><span class="sxs-lookup"><span data-stu-id="7c0dd-123">TABLE_GUID</span></span>|<span data-ttu-id="7c0dd-124">Guid</span><span class="sxs-lookup"><span data-stu-id="7c0dd-124">Guid</span></span>|  
|<span data-ttu-id="7c0dd-125">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="7c0dd-125">DESCRIPTION</span></span>|<span data-ttu-id="7c0dd-126">String</span><span class="sxs-lookup"><span data-stu-id="7c0dd-126">String</span></span>|  
|<span data-ttu-id="7c0dd-127">TABLE_PROPID</span><span class="sxs-lookup"><span data-stu-id="7c0dd-127">TABLE_PROPID</span></span>|<span data-ttu-id="7c0dd-128">Int64</span><span class="sxs-lookup"><span data-stu-id="7c0dd-128">Int64</span></span>|  
|<span data-ttu-id="7c0dd-129">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="7c0dd-129">DATE_CREATED</span></span>|<span data-ttu-id="7c0dd-130">DateTime</span><span class="sxs-lookup"><span data-stu-id="7c0dd-130">DateTime</span></span>|  
|<span data-ttu-id="7c0dd-131">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="7c0dd-131">DATE_MODIFIED</span></span>|<span data-ttu-id="7c0dd-132">DateTime</span><span class="sxs-lookup"><span data-stu-id="7c0dd-132">DateTime</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="7c0dd-133">Столбцы</span><span class="sxs-lookup"><span data-stu-id="7c0dd-133">Columns</span></span>  
  
|<span data-ttu-id="7c0dd-134">ColumnName</span><span class="sxs-lookup"><span data-stu-id="7c0dd-134">ColumnName</span></span>|<span data-ttu-id="7c0dd-135">DataType</span><span class="sxs-lookup"><span data-stu-id="7c0dd-135">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="7c0dd-136">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="7c0dd-136">TABLE_CATALOG</span></span>|<span data-ttu-id="7c0dd-137">String</span><span class="sxs-lookup"><span data-stu-id="7c0dd-137">String</span></span>|  
|<span data-ttu-id="7c0dd-138">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="7c0dd-138">TABLE_SCHEMA</span></span>|<span data-ttu-id="7c0dd-139">String</span><span class="sxs-lookup"><span data-stu-id="7c0dd-139">String</span></span>|  
|<span data-ttu-id="7c0dd-140">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="7c0dd-140">TABLE_NAME</span></span>|<span data-ttu-id="7c0dd-141">String</span><span class="sxs-lookup"><span data-stu-id="7c0dd-141">String</span></span>|  
|<span data-ttu-id="7c0dd-142">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="7c0dd-142">COLUMN_NAME</span></span>|<span data-ttu-id="7c0dd-143">String</span><span class="sxs-lookup"><span data-stu-id="7c0dd-143">String</span></span>|  
|<span data-ttu-id="7c0dd-144">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="7c0dd-144">COLUMN_GUID</span></span>|<span data-ttu-id="7c0dd-145">Guid</span><span class="sxs-lookup"><span data-stu-id="7c0dd-145">Guid</span></span>|  
|<span data-ttu-id="7c0dd-146">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="7c0dd-146">COLUMN_PROPID</span></span>|<span data-ttu-id="7c0dd-147">Int64</span><span class="sxs-lookup"><span data-stu-id="7c0dd-147">Int64</span></span>|  
|<span data-ttu-id="7c0dd-148">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="7c0dd-148">ORDINAL_POSITION</span></span>|<span data-ttu-id="7c0dd-149">Int64</span><span class="sxs-lookup"><span data-stu-id="7c0dd-149">Int64</span></span>|  
|<span data-ttu-id="7c0dd-150">COLUMN_HASDEFAULT</span><span class="sxs-lookup"><span data-stu-id="7c0dd-150">COLUMN_HASDEFAULT</span></span>|<span data-ttu-id="7c0dd-151">логический</span><span class="sxs-lookup"><span data-stu-id="7c0dd-151">Boolean</span></span>|  
|<span data-ttu-id="7c0dd-152">COLUMN_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="7c0dd-152">COLUMN_DEFAULT</span></span>|<span data-ttu-id="7c0dd-153">String</span><span class="sxs-lookup"><span data-stu-id="7c0dd-153">String</span></span>|  
|<span data-ttu-id="7c0dd-154">COLUMN_FLAGS</span><span class="sxs-lookup"><span data-stu-id="7c0dd-154">COLUMN_FLAGS</span></span>|<span data-ttu-id="7c0dd-155">Int64</span><span class="sxs-lookup"><span data-stu-id="7c0dd-155">Int64</span></span>|  
|<span data-ttu-id="7c0dd-156">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="7c0dd-156">IS_NULLABLE</span></span>|<span data-ttu-id="7c0dd-157">логический</span><span class="sxs-lookup"><span data-stu-id="7c0dd-157">Boolean</span></span>|  
|<span data-ttu-id="7c0dd-158">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="7c0dd-158">DATA_TYPE</span></span>|<span data-ttu-id="7c0dd-159">Int32</span><span class="sxs-lookup"><span data-stu-id="7c0dd-159">Int32</span></span>|  
|<span data-ttu-id="7c0dd-160">TYPE_GUID</span><span class="sxs-lookup"><span data-stu-id="7c0dd-160">TYPE_GUID</span></span>|<span data-ttu-id="7c0dd-161">Guid</span><span class="sxs-lookup"><span data-stu-id="7c0dd-161">Guid</span></span>|  
|<span data-ttu-id="7c0dd-162">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="7c0dd-162">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="7c0dd-163">Int64</span><span class="sxs-lookup"><span data-stu-id="7c0dd-163">Int64</span></span>|  
|<span data-ttu-id="7c0dd-164">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="7c0dd-164">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="7c0dd-165">Int64</span><span class="sxs-lookup"><span data-stu-id="7c0dd-165">Int64</span></span>|  
|<span data-ttu-id="7c0dd-166">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="7c0dd-166">NUMERIC_PRECISION</span></span>|<span data-ttu-id="7c0dd-167">Int32</span><span class="sxs-lookup"><span data-stu-id="7c0dd-167">Int32</span></span>|  
|<span data-ttu-id="7c0dd-168">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="7c0dd-168">NUMERIC_SCALE</span></span>|<span data-ttu-id="7c0dd-169">Int16</span><span class="sxs-lookup"><span data-stu-id="7c0dd-169">Int16</span></span>|  
|<span data-ttu-id="7c0dd-170">DATETIME_PRECISION</span><span class="sxs-lookup"><span data-stu-id="7c0dd-170">DATETIME_PRECISION</span></span>|<span data-ttu-id="7c0dd-171">Int64</span><span class="sxs-lookup"><span data-stu-id="7c0dd-171">Int64</span></span>|  
|<span data-ttu-id="7c0dd-172">CHARACTER_SET_CATALOG</span><span class="sxs-lookup"><span data-stu-id="7c0dd-172">CHARACTER_SET_CATALOG</span></span>|<span data-ttu-id="7c0dd-173">String</span><span class="sxs-lookup"><span data-stu-id="7c0dd-173">String</span></span>|  
|<span data-ttu-id="7c0dd-174">CHARACTER_SET_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="7c0dd-174">CHARACTER_SET_SCHEMA</span></span>|<span data-ttu-id="7c0dd-175">String</span><span class="sxs-lookup"><span data-stu-id="7c0dd-175">String</span></span>|  
|<span data-ttu-id="7c0dd-176">CHARACTER_SET_NAME</span><span class="sxs-lookup"><span data-stu-id="7c0dd-176">CHARACTER_SET_NAME</span></span>|<span data-ttu-id="7c0dd-177">String</span><span class="sxs-lookup"><span data-stu-id="7c0dd-177">String</span></span>|  
|<span data-ttu-id="7c0dd-178">COLLATION_CATALOG</span><span class="sxs-lookup"><span data-stu-id="7c0dd-178">COLLATION_CATALOG</span></span>|<span data-ttu-id="7c0dd-179">String</span><span class="sxs-lookup"><span data-stu-id="7c0dd-179">String</span></span>|  
|<span data-ttu-id="7c0dd-180">COLLATION_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="7c0dd-180">COLLATION_SCHEMA</span></span>|<span data-ttu-id="7c0dd-181">String</span><span class="sxs-lookup"><span data-stu-id="7c0dd-181">String</span></span>|  
|<span data-ttu-id="7c0dd-182">COLLATION_NAME</span><span class="sxs-lookup"><span data-stu-id="7c0dd-182">COLLATION_NAME</span></span>|<span data-ttu-id="7c0dd-183">String</span><span class="sxs-lookup"><span data-stu-id="7c0dd-183">String</span></span>|  
|<span data-ttu-id="7c0dd-184">DOMAIN_CATALOG</span><span class="sxs-lookup"><span data-stu-id="7c0dd-184">DOMAIN_CATALOG</span></span>|<span data-ttu-id="7c0dd-185">String</span><span class="sxs-lookup"><span data-stu-id="7c0dd-185">String</span></span>|  
|<span data-ttu-id="7c0dd-186">DOMAIN_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="7c0dd-186">DOMAIN_SCHEMA</span></span>|<span data-ttu-id="7c0dd-187">String</span><span class="sxs-lookup"><span data-stu-id="7c0dd-187">String</span></span>|  
|<span data-ttu-id="7c0dd-188">DOMAIN_NAME</span><span class="sxs-lookup"><span data-stu-id="7c0dd-188">DOMAIN_NAME</span></span>|<span data-ttu-id="7c0dd-189">String</span><span class="sxs-lookup"><span data-stu-id="7c0dd-189">String</span></span>|  
|<span data-ttu-id="7c0dd-190">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="7c0dd-190">DESCRIPTION</span></span>|<span data-ttu-id="7c0dd-191">String</span><span class="sxs-lookup"><span data-stu-id="7c0dd-191">String</span></span>|  
|<span data-ttu-id="7c0dd-192">COLUMN_LCID</span><span class="sxs-lookup"><span data-stu-id="7c0dd-192">COLUMN_LCID</span></span>|<span data-ttu-id="7c0dd-193">Int32</span><span class="sxs-lookup"><span data-stu-id="7c0dd-193">Int32</span></span>|  
|<span data-ttu-id="7c0dd-194">COLUMN_COMPFLAGS</span><span class="sxs-lookup"><span data-stu-id="7c0dd-194">COLUMN_COMPFLAGS</span></span>|<span data-ttu-id="7c0dd-195">Int32</span><span class="sxs-lookup"><span data-stu-id="7c0dd-195">Int32</span></span>|  
|<span data-ttu-id="7c0dd-196">COLUMN_SORTID</span><span class="sxs-lookup"><span data-stu-id="7c0dd-196">COLUMN_SORTID</span></span>|<span data-ttu-id="7c0dd-197">Int32</span><span class="sxs-lookup"><span data-stu-id="7c0dd-197">Int32</span></span>|  
|<span data-ttu-id="7c0dd-198">COLUMN_TDSCOLLATION</span><span class="sxs-lookup"><span data-stu-id="7c0dd-198">COLUMN_TDSCOLLATION</span></span>|<span data-ttu-id="7c0dd-199">Byte[]</span><span class="sxs-lookup"><span data-stu-id="7c0dd-199">Byte[]</span></span>|  
|<span data-ttu-id="7c0dd-200">IS_COMPUTED</span><span class="sxs-lookup"><span data-stu-id="7c0dd-200">IS_COMPUTED</span></span>|<span data-ttu-id="7c0dd-201">логический</span><span class="sxs-lookup"><span data-stu-id="7c0dd-201">Boolean</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="7c0dd-202">Процедуры</span><span class="sxs-lookup"><span data-stu-id="7c0dd-202">Procedures</span></span>  
  
|<span data-ttu-id="7c0dd-203">ColumnName</span><span class="sxs-lookup"><span data-stu-id="7c0dd-203">ColumnName</span></span>|<span data-ttu-id="7c0dd-204">DataType</span><span class="sxs-lookup"><span data-stu-id="7c0dd-204">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="7c0dd-205">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="7c0dd-205">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="7c0dd-206">String</span><span class="sxs-lookup"><span data-stu-id="7c0dd-206">String</span></span>|  
|<span data-ttu-id="7c0dd-207">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="7c0dd-207">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="7c0dd-208">String</span><span class="sxs-lookup"><span data-stu-id="7c0dd-208">String</span></span>|  
|<span data-ttu-id="7c0dd-209">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="7c0dd-209">PROCEDURE_NAME</span></span>|<span data-ttu-id="7c0dd-210">String</span><span class="sxs-lookup"><span data-stu-id="7c0dd-210">String</span></span>|  
|<span data-ttu-id="7c0dd-211">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="7c0dd-211">PROCEDURE_TYPE</span></span>|<span data-ttu-id="7c0dd-212">Int16</span><span class="sxs-lookup"><span data-stu-id="7c0dd-212">Int16</span></span>|  
|<span data-ttu-id="7c0dd-213">PROCEDURE_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="7c0dd-213">PROCEDURE_DEFINITION</span></span>|<span data-ttu-id="7c0dd-214">String</span><span class="sxs-lookup"><span data-stu-id="7c0dd-214">String</span></span>|  
|<span data-ttu-id="7c0dd-215">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="7c0dd-215">DESCRIPTION</span></span>|<span data-ttu-id="7c0dd-216">String</span><span class="sxs-lookup"><span data-stu-id="7c0dd-216">String</span></span>|  
|<span data-ttu-id="7c0dd-217">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="7c0dd-217">DATE_CREATED</span></span>|<span data-ttu-id="7c0dd-218">DateTime</span><span class="sxs-lookup"><span data-stu-id="7c0dd-218">DateTime</span></span>|  
|<span data-ttu-id="7c0dd-219">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="7c0dd-219">DATE_MODIFIED</span></span>|<span data-ttu-id="7c0dd-220">DateTime</span><span class="sxs-lookup"><span data-stu-id="7c0dd-220">DateTime</span></span>|  
  
### <a name="procedureparameters"></a><span data-ttu-id="7c0dd-221">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="7c0dd-221">ProcedureParameters</span></span>  
  
|<span data-ttu-id="7c0dd-222">ColumnName</span><span class="sxs-lookup"><span data-stu-id="7c0dd-222">ColumnName</span></span>|<span data-ttu-id="7c0dd-223">DataType</span><span class="sxs-lookup"><span data-stu-id="7c0dd-223">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="7c0dd-224">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="7c0dd-224">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="7c0dd-225">String</span><span class="sxs-lookup"><span data-stu-id="7c0dd-225">String</span></span>|  
|<span data-ttu-id="7c0dd-226">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="7c0dd-226">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="7c0dd-227">String</span><span class="sxs-lookup"><span data-stu-id="7c0dd-227">String</span></span>|  
|<span data-ttu-id="7c0dd-228">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="7c0dd-228">PROCEDURE_NAME</span></span>|<span data-ttu-id="7c0dd-229">String</span><span class="sxs-lookup"><span data-stu-id="7c0dd-229">String</span></span>|  
|<span data-ttu-id="7c0dd-230">PARAMETER_NAME</span><span class="sxs-lookup"><span data-stu-id="7c0dd-230">PARAMETER_NAME</span></span>|<span data-ttu-id="7c0dd-231">String</span><span class="sxs-lookup"><span data-stu-id="7c0dd-231">String</span></span>|  
|<span data-ttu-id="7c0dd-232">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="7c0dd-232">ORDINAL_POSITION</span></span>|<span data-ttu-id="7c0dd-233">Int32</span><span class="sxs-lookup"><span data-stu-id="7c0dd-233">Int32</span></span>|  
|<span data-ttu-id="7c0dd-234">PARAMETER_TYPE</span><span class="sxs-lookup"><span data-stu-id="7c0dd-234">PARAMETER_TYPE</span></span>|<span data-ttu-id="7c0dd-235">Int32</span><span class="sxs-lookup"><span data-stu-id="7c0dd-235">Int32</span></span>|  
|<span data-ttu-id="7c0dd-236">PARAMETER_HASDEFAULT</span><span class="sxs-lookup"><span data-stu-id="7c0dd-236">PARAMETER_HASDEFAULT</span></span>|<span data-ttu-id="7c0dd-237">логический</span><span class="sxs-lookup"><span data-stu-id="7c0dd-237">Boolean</span></span>|  
|<span data-ttu-id="7c0dd-238">PARAMETER_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="7c0dd-238">PARAMETER_DEFAULT</span></span>|<span data-ttu-id="7c0dd-239">String</span><span class="sxs-lookup"><span data-stu-id="7c0dd-239">String</span></span>|  
|<span data-ttu-id="7c0dd-240">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="7c0dd-240">IS_NULLABLE</span></span>|<span data-ttu-id="7c0dd-241">логический</span><span class="sxs-lookup"><span data-stu-id="7c0dd-241">Boolean</span></span>|  
|<span data-ttu-id="7c0dd-242">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="7c0dd-242">DATA_TYPE</span></span>|<span data-ttu-id="7c0dd-243">Int32</span><span class="sxs-lookup"><span data-stu-id="7c0dd-243">Int32</span></span>|  
|<span data-ttu-id="7c0dd-244">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="7c0dd-244">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="7c0dd-245">Int64</span><span class="sxs-lookup"><span data-stu-id="7c0dd-245">Int64</span></span>|  
|<span data-ttu-id="7c0dd-246">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="7c0dd-246">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="7c0dd-247">Int64</span><span class="sxs-lookup"><span data-stu-id="7c0dd-247">Int64</span></span>|  
|<span data-ttu-id="7c0dd-248">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="7c0dd-248">NUMERIC_PRECISION</span></span>|<span data-ttu-id="7c0dd-249">Int32</span><span class="sxs-lookup"><span data-stu-id="7c0dd-249">Int32</span></span>|  
|<span data-ttu-id="7c0dd-250">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="7c0dd-250">NUMERIC_SCALE</span></span>|<span data-ttu-id="7c0dd-251">Int16</span><span class="sxs-lookup"><span data-stu-id="7c0dd-251">Int16</span></span>|  
|<span data-ttu-id="7c0dd-252">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="7c0dd-252">DESCRIPTION</span></span>|<span data-ttu-id="7c0dd-253">String</span><span class="sxs-lookup"><span data-stu-id="7c0dd-253">String</span></span>|  
|<span data-ttu-id="7c0dd-254">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="7c0dd-254">TYPE_NAME</span></span>|<span data-ttu-id="7c0dd-255">String</span><span class="sxs-lookup"><span data-stu-id="7c0dd-255">String</span></span>|  
|<span data-ttu-id="7c0dd-256">LOCAL_TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="7c0dd-256">LOCAL_TYPE_NAME</span></span>|<span data-ttu-id="7c0dd-257">String</span><span class="sxs-lookup"><span data-stu-id="7c0dd-257">String</span></span>|  
  
### <a name="catalog"></a><span data-ttu-id="7c0dd-258">Catalog</span><span class="sxs-lookup"><span data-stu-id="7c0dd-258">Catalog</span></span>  
  
|<span data-ttu-id="7c0dd-259">ColumnName</span><span class="sxs-lookup"><span data-stu-id="7c0dd-259">ColumnName</span></span>|<span data-ttu-id="7c0dd-260">DataType</span><span class="sxs-lookup"><span data-stu-id="7c0dd-260">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="7c0dd-261">CATALOG_NAME</span><span class="sxs-lookup"><span data-stu-id="7c0dd-261">CATALOG_NAME</span></span>|<span data-ttu-id="7c0dd-262">String</span><span class="sxs-lookup"><span data-stu-id="7c0dd-262">String</span></span>|  
|<span data-ttu-id="7c0dd-263">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="7c0dd-263">DESCRIPTION</span></span>|<span data-ttu-id="7c0dd-264">String</span><span class="sxs-lookup"><span data-stu-id="7c0dd-264">String</span></span>|  
  
### <a name="indexes"></a><span data-ttu-id="7c0dd-265">Индексы</span><span class="sxs-lookup"><span data-stu-id="7c0dd-265">Indexes</span></span>  
  
|<span data-ttu-id="7c0dd-266">ColumnName</span><span class="sxs-lookup"><span data-stu-id="7c0dd-266">ColumnName</span></span>|<span data-ttu-id="7c0dd-267">DataType</span><span class="sxs-lookup"><span data-stu-id="7c0dd-267">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="7c0dd-268">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="7c0dd-268">TABLE_CATALOG</span></span>|<span data-ttu-id="7c0dd-269">String</span><span class="sxs-lookup"><span data-stu-id="7c0dd-269">String</span></span>|  
|<span data-ttu-id="7c0dd-270">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="7c0dd-270">TABLE_SCHEMA</span></span>|<span data-ttu-id="7c0dd-271">String</span><span class="sxs-lookup"><span data-stu-id="7c0dd-271">String</span></span>|  
|<span data-ttu-id="7c0dd-272">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="7c0dd-272">TABLE_NAME</span></span>|<span data-ttu-id="7c0dd-273">String</span><span class="sxs-lookup"><span data-stu-id="7c0dd-273">String</span></span>|  
|<span data-ttu-id="7c0dd-274">INDEX_CATALOG</span><span class="sxs-lookup"><span data-stu-id="7c0dd-274">INDEX_CATALOG</span></span>|<span data-ttu-id="7c0dd-275">String</span><span class="sxs-lookup"><span data-stu-id="7c0dd-275">String</span></span>|  
|<span data-ttu-id="7c0dd-276">INDEX_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="7c0dd-276">INDEX_SCHEMA</span></span>|<span data-ttu-id="7c0dd-277">String</span><span class="sxs-lookup"><span data-stu-id="7c0dd-277">String</span></span>|  
|<span data-ttu-id="7c0dd-278">INDEX_NAME</span><span class="sxs-lookup"><span data-stu-id="7c0dd-278">INDEX_NAME</span></span>|<span data-ttu-id="7c0dd-279">String</span><span class="sxs-lookup"><span data-stu-id="7c0dd-279">String</span></span>|  
|<span data-ttu-id="7c0dd-280">PRIMARY_KEY</span><span class="sxs-lookup"><span data-stu-id="7c0dd-280">PRIMARY_KEY</span></span>|<span data-ttu-id="7c0dd-281">логический</span><span class="sxs-lookup"><span data-stu-id="7c0dd-281">Boolean</span></span>|  
|<span data-ttu-id="7c0dd-282">UNIQUE</span><span class="sxs-lookup"><span data-stu-id="7c0dd-282">UNIQUE</span></span>|<span data-ttu-id="7c0dd-283">логический</span><span class="sxs-lookup"><span data-stu-id="7c0dd-283">Boolean</span></span>|  
|<span data-ttu-id="7c0dd-284">CLUSTERED</span><span class="sxs-lookup"><span data-stu-id="7c0dd-284">CLUSTERED</span></span>|<span data-ttu-id="7c0dd-285">логический</span><span class="sxs-lookup"><span data-stu-id="7c0dd-285">Boolean</span></span>|  
|<span data-ttu-id="7c0dd-286">ТИП</span><span class="sxs-lookup"><span data-stu-id="7c0dd-286">TYPE</span></span>|<span data-ttu-id="7c0dd-287">Int32</span><span class="sxs-lookup"><span data-stu-id="7c0dd-287">Int32</span></span>|  
|<span data-ttu-id="7c0dd-288">FILL_FACTOR</span><span class="sxs-lookup"><span data-stu-id="7c0dd-288">FILL_FACTOR</span></span>|<span data-ttu-id="7c0dd-289">Int32</span><span class="sxs-lookup"><span data-stu-id="7c0dd-289">Int32</span></span>|  
|<span data-ttu-id="7c0dd-290">INITIAL_SIZE</span><span class="sxs-lookup"><span data-stu-id="7c0dd-290">INITIAL_SIZE</span></span>|<span data-ttu-id="7c0dd-291">Int32</span><span class="sxs-lookup"><span data-stu-id="7c0dd-291">Int32</span></span>|  
|<span data-ttu-id="7c0dd-292">NULLS</span><span class="sxs-lookup"><span data-stu-id="7c0dd-292">NULLS</span></span>|<span data-ttu-id="7c0dd-293">Int32</span><span class="sxs-lookup"><span data-stu-id="7c0dd-293">Int32</span></span>|  
|<span data-ttu-id="7c0dd-294">SORT_BOOKMARKS</span><span class="sxs-lookup"><span data-stu-id="7c0dd-294">SORT_BOOKMARKS</span></span>|<span data-ttu-id="7c0dd-295">логический</span><span class="sxs-lookup"><span data-stu-id="7c0dd-295">Boolean</span></span>|  
|<span data-ttu-id="7c0dd-296">AUTO_UPDATE</span><span class="sxs-lookup"><span data-stu-id="7c0dd-296">AUTO_UPDATE</span></span>|<span data-ttu-id="7c0dd-297">логический</span><span class="sxs-lookup"><span data-stu-id="7c0dd-297">Boolean</span></span>|  
|<span data-ttu-id="7c0dd-298">NULL_COLLATION</span><span class="sxs-lookup"><span data-stu-id="7c0dd-298">NULL_COLLATION</span></span>|<span data-ttu-id="7c0dd-299">Int32</span><span class="sxs-lookup"><span data-stu-id="7c0dd-299">Int32</span></span>|  
|<span data-ttu-id="7c0dd-300">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="7c0dd-300">ORDINAL_POSITION</span></span>|<span data-ttu-id="7c0dd-301">Int64</span><span class="sxs-lookup"><span data-stu-id="7c0dd-301">Int64</span></span>|  
|<span data-ttu-id="7c0dd-302">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="7c0dd-302">COLUMN_NAME</span></span>|<span data-ttu-id="7c0dd-303">String</span><span class="sxs-lookup"><span data-stu-id="7c0dd-303">String</span></span>|  
|<span data-ttu-id="7c0dd-304">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="7c0dd-304">COLUMN_GUID</span></span>|<span data-ttu-id="7c0dd-305">Guid</span><span class="sxs-lookup"><span data-stu-id="7c0dd-305">Guid</span></span>|  
|<span data-ttu-id="7c0dd-306">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="7c0dd-306">COLUMN_PROPID</span></span>|<span data-ttu-id="7c0dd-307">Int64</span><span class="sxs-lookup"><span data-stu-id="7c0dd-307">Int64</span></span>|  
|<span data-ttu-id="7c0dd-308">COLLATION</span><span class="sxs-lookup"><span data-stu-id="7c0dd-308">COLLATION</span></span>|<span data-ttu-id="7c0dd-309">Int16</span><span class="sxs-lookup"><span data-stu-id="7c0dd-309">Int16</span></span>|  
|<span data-ttu-id="7c0dd-310">CARDINALITY</span><span class="sxs-lookup"><span data-stu-id="7c0dd-310">CARDINALITY</span></span>|<span data-ttu-id="7c0dd-311">Decimal</span><span class="sxs-lookup"><span data-stu-id="7c0dd-311">Decimal</span></span>|  
|<span data-ttu-id="7c0dd-312">PAGES</span><span class="sxs-lookup"><span data-stu-id="7c0dd-312">PAGES</span></span>|<span data-ttu-id="7c0dd-313">Int32</span><span class="sxs-lookup"><span data-stu-id="7c0dd-313">Int32</span></span>|  
|<span data-ttu-id="7c0dd-314">FILTER_CONDITION</span><span class="sxs-lookup"><span data-stu-id="7c0dd-314">FILTER_CONDITION</span></span>|<span data-ttu-id="7c0dd-315">String</span><span class="sxs-lookup"><span data-stu-id="7c0dd-315">String</span></span>|  
|<span data-ttu-id="7c0dd-316">INTEGRATED</span><span class="sxs-lookup"><span data-stu-id="7c0dd-316">INTEGRATED</span></span>|<span data-ttu-id="7c0dd-317">логический</span><span class="sxs-lookup"><span data-stu-id="7c0dd-317">Boolean</span></span>|  
  
## <a name="microsoft-oracle-ole-db-provider"></a><span data-ttu-id="7c0dd-318">Поставщик Microsoft OLE DB для Oracle</span><span class="sxs-lookup"><span data-stu-id="7c0dd-318">Microsoft Oracle OLE DB Provider</span></span>  
 <span data-ttu-id="7c0dd-319">Драйвер OLE DB для Oracle (Майкрософт) поддерживает следующие специальные коллекции схем в дополнение к общим коллекциям.</span><span class="sxs-lookup"><span data-stu-id="7c0dd-319">The Microsoft Oracle OLE DB Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
- <span data-ttu-id="7c0dd-320">Таблицы</span><span class="sxs-lookup"><span data-stu-id="7c0dd-320">Tables</span></span>  
  
- <span data-ttu-id="7c0dd-321">Столбцы</span><span class="sxs-lookup"><span data-stu-id="7c0dd-321">Columns</span></span>  
  
- <span data-ttu-id="7c0dd-322">Процедуры</span><span class="sxs-lookup"><span data-stu-id="7c0dd-322">Procedures</span></span>  
  
- <span data-ttu-id="7c0dd-323">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="7c0dd-323">ProcedureColumns</span></span>  
  
- <span data-ttu-id="7c0dd-324">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="7c0dd-324">ProcedureParameters</span></span>  
  
- <span data-ttu-id="7c0dd-325">Представления</span><span class="sxs-lookup"><span data-stu-id="7c0dd-325">Views</span></span>  
  
- <span data-ttu-id="7c0dd-326">Индексы</span><span class="sxs-lookup"><span data-stu-id="7c0dd-326">Indexes</span></span>  
  
### <a name="tables"></a><span data-ttu-id="7c0dd-327">Таблицы</span><span class="sxs-lookup"><span data-stu-id="7c0dd-327">Tables</span></span>  
  
|<span data-ttu-id="7c0dd-328">ColumnName</span><span class="sxs-lookup"><span data-stu-id="7c0dd-328">ColumnName</span></span>|<span data-ttu-id="7c0dd-329">DataType</span><span class="sxs-lookup"><span data-stu-id="7c0dd-329">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="7c0dd-330">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="7c0dd-330">TABLE_CATALOG</span></span>|<span data-ttu-id="7c0dd-331">String</span><span class="sxs-lookup"><span data-stu-id="7c0dd-331">String</span></span>|  
|<span data-ttu-id="7c0dd-332">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="7c0dd-332">TABLE_SCHEMA</span></span>|<span data-ttu-id="7c0dd-333">String</span><span class="sxs-lookup"><span data-stu-id="7c0dd-333">String</span></span>|  
|<span data-ttu-id="7c0dd-334">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="7c0dd-334">TABLE_NAME</span></span>|<span data-ttu-id="7c0dd-335">String</span><span class="sxs-lookup"><span data-stu-id="7c0dd-335">String</span></span>|  
|<span data-ttu-id="7c0dd-336">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="7c0dd-336">TABLE_TYPE</span></span>|<span data-ttu-id="7c0dd-337">String</span><span class="sxs-lookup"><span data-stu-id="7c0dd-337">String</span></span>|  
|<span data-ttu-id="7c0dd-338">TABLE_GUID</span><span class="sxs-lookup"><span data-stu-id="7c0dd-338">TABLE_GUID</span></span>|<span data-ttu-id="7c0dd-339">Guid</span><span class="sxs-lookup"><span data-stu-id="7c0dd-339">Guid</span></span>|  
|<span data-ttu-id="7c0dd-340">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="7c0dd-340">DESCRIPTION</span></span>|<span data-ttu-id="7c0dd-341">String</span><span class="sxs-lookup"><span data-stu-id="7c0dd-341">String</span></span>|  
|<span data-ttu-id="7c0dd-342">TABLE_PROPID</span><span class="sxs-lookup"><span data-stu-id="7c0dd-342">TABLE_PROPID</span></span>|<span data-ttu-id="7c0dd-343">Int64</span><span class="sxs-lookup"><span data-stu-id="7c0dd-343">Int64</span></span>|  
|<span data-ttu-id="7c0dd-344">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="7c0dd-344">DATE_CREATED</span></span>|<span data-ttu-id="7c0dd-345">DateTime</span><span class="sxs-lookup"><span data-stu-id="7c0dd-345">DateTime</span></span>|  
|<span data-ttu-id="7c0dd-346">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="7c0dd-346">DATE_MODIFIED</span></span>|<span data-ttu-id="7c0dd-347">DateTime</span><span class="sxs-lookup"><span data-stu-id="7c0dd-347">DateTime</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="7c0dd-348">Столбцы</span><span class="sxs-lookup"><span data-stu-id="7c0dd-348">Columns</span></span>  
  
|<span data-ttu-id="7c0dd-349">ColumnName</span><span class="sxs-lookup"><span data-stu-id="7c0dd-349">ColumnName</span></span>|<span data-ttu-id="7c0dd-350">DataType</span><span class="sxs-lookup"><span data-stu-id="7c0dd-350">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="7c0dd-351">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="7c0dd-351">TABLE_CATALOG</span></span>|<span data-ttu-id="7c0dd-352">String</span><span class="sxs-lookup"><span data-stu-id="7c0dd-352">String</span></span>|  
|<span data-ttu-id="7c0dd-353">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="7c0dd-353">TABLE_SCHEMA</span></span>|<span data-ttu-id="7c0dd-354">String</span><span class="sxs-lookup"><span data-stu-id="7c0dd-354">String</span></span>|  
|<span data-ttu-id="7c0dd-355">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="7c0dd-355">TABLE_NAME</span></span>|<span data-ttu-id="7c0dd-356">String</span><span class="sxs-lookup"><span data-stu-id="7c0dd-356">String</span></span>|  
|<span data-ttu-id="7c0dd-357">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="7c0dd-357">COLUMN_NAME</span></span>|<span data-ttu-id="7c0dd-358">String</span><span class="sxs-lookup"><span data-stu-id="7c0dd-358">String</span></span>|  
|<span data-ttu-id="7c0dd-359">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="7c0dd-359">COLUMN_GUID</span></span>|<span data-ttu-id="7c0dd-360">Guid</span><span class="sxs-lookup"><span data-stu-id="7c0dd-360">Guid</span></span>|  
|<span data-ttu-id="7c0dd-361">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="7c0dd-361">COLUMN_PROPID</span></span>|<span data-ttu-id="7c0dd-362">Int64</span><span class="sxs-lookup"><span data-stu-id="7c0dd-362">Int64</span></span>|  
|<span data-ttu-id="7c0dd-363">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="7c0dd-363">ORDINAL_POSITION</span></span>|<span data-ttu-id="7c0dd-364">Int64</span><span class="sxs-lookup"><span data-stu-id="7c0dd-364">Int64</span></span>|  
|<span data-ttu-id="7c0dd-365">COLUMN_HASDEFAULT</span><span class="sxs-lookup"><span data-stu-id="7c0dd-365">COLUMN_HASDEFAULT</span></span>|<span data-ttu-id="7c0dd-366">логический</span><span class="sxs-lookup"><span data-stu-id="7c0dd-366">Boolean</span></span>|  
|<span data-ttu-id="7c0dd-367">COLUMN_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="7c0dd-367">COLUMN_DEFAULT</span></span>|<span data-ttu-id="7c0dd-368">String</span><span class="sxs-lookup"><span data-stu-id="7c0dd-368">String</span></span>|  
|<span data-ttu-id="7c0dd-369">COLUMN_FLAGS</span><span class="sxs-lookup"><span data-stu-id="7c0dd-369">COLUMN_FLAGS</span></span>|<span data-ttu-id="7c0dd-370">Int64</span><span class="sxs-lookup"><span data-stu-id="7c0dd-370">Int64</span></span>|  
|<span data-ttu-id="7c0dd-371">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="7c0dd-371">IS_NULLABLE</span></span>|<span data-ttu-id="7c0dd-372">логический</span><span class="sxs-lookup"><span data-stu-id="7c0dd-372">Boolean</span></span>|  
|<span data-ttu-id="7c0dd-373">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="7c0dd-373">DATA_TYPE</span></span>|<span data-ttu-id="7c0dd-374">Int32</span><span class="sxs-lookup"><span data-stu-id="7c0dd-374">Int32</span></span>|  
|<span data-ttu-id="7c0dd-375">TYPE_GUID</span><span class="sxs-lookup"><span data-stu-id="7c0dd-375">TYPE_GUID</span></span>|<span data-ttu-id="7c0dd-376">Guid</span><span class="sxs-lookup"><span data-stu-id="7c0dd-376">Guid</span></span>|  
|<span data-ttu-id="7c0dd-377">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="7c0dd-377">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="7c0dd-378">Int64</span><span class="sxs-lookup"><span data-stu-id="7c0dd-378">Int64</span></span>|  
|<span data-ttu-id="7c0dd-379">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="7c0dd-379">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="7c0dd-380">Int64</span><span class="sxs-lookup"><span data-stu-id="7c0dd-380">Int64</span></span>|  
|<span data-ttu-id="7c0dd-381">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="7c0dd-381">NUMERIC_PRECISION</span></span>|<span data-ttu-id="7c0dd-382">Int32</span><span class="sxs-lookup"><span data-stu-id="7c0dd-382">Int32</span></span>|  
|<span data-ttu-id="7c0dd-383">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="7c0dd-383">NUMERIC_SCALE</span></span>|<span data-ttu-id="7c0dd-384">Int16</span><span class="sxs-lookup"><span data-stu-id="7c0dd-384">Int16</span></span>|  
|<span data-ttu-id="7c0dd-385">DATETIME_PRECISION</span><span class="sxs-lookup"><span data-stu-id="7c0dd-385">DATETIME_PRECISION</span></span>|<span data-ttu-id="7c0dd-386">Int64</span><span class="sxs-lookup"><span data-stu-id="7c0dd-386">Int64</span></span>|  
|<span data-ttu-id="7c0dd-387">CHARACTER_SET_CATALOG</span><span class="sxs-lookup"><span data-stu-id="7c0dd-387">CHARACTER_SET_CATALOG</span></span>|<span data-ttu-id="7c0dd-388">String</span><span class="sxs-lookup"><span data-stu-id="7c0dd-388">String</span></span>|  
|<span data-ttu-id="7c0dd-389">CHARACTER_SET_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="7c0dd-389">CHARACTER_SET_SCHEMA</span></span>|<span data-ttu-id="7c0dd-390">String</span><span class="sxs-lookup"><span data-stu-id="7c0dd-390">String</span></span>|  
|<span data-ttu-id="7c0dd-391">CHARACTER_SET_NAME</span><span class="sxs-lookup"><span data-stu-id="7c0dd-391">CHARACTER_SET_NAME</span></span>|<span data-ttu-id="7c0dd-392">String</span><span class="sxs-lookup"><span data-stu-id="7c0dd-392">String</span></span>|  
|<span data-ttu-id="7c0dd-393">COLLATION_CATALOG</span><span class="sxs-lookup"><span data-stu-id="7c0dd-393">COLLATION_CATALOG</span></span>|<span data-ttu-id="7c0dd-394">String</span><span class="sxs-lookup"><span data-stu-id="7c0dd-394">String</span></span>|  
|<span data-ttu-id="7c0dd-395">COLLATION_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="7c0dd-395">COLLATION_SCHEMA</span></span>|<span data-ttu-id="7c0dd-396">String</span><span class="sxs-lookup"><span data-stu-id="7c0dd-396">String</span></span>|  
|<span data-ttu-id="7c0dd-397">COLLATION_NAME</span><span class="sxs-lookup"><span data-stu-id="7c0dd-397">COLLATION_NAME</span></span>|<span data-ttu-id="7c0dd-398">String</span><span class="sxs-lookup"><span data-stu-id="7c0dd-398">String</span></span>|  
|<span data-ttu-id="7c0dd-399">DOMAIN_CATALOG</span><span class="sxs-lookup"><span data-stu-id="7c0dd-399">DOMAIN_CATALOG</span></span>|<span data-ttu-id="7c0dd-400">String</span><span class="sxs-lookup"><span data-stu-id="7c0dd-400">String</span></span>|  
|<span data-ttu-id="7c0dd-401">DOMAIN_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="7c0dd-401">DOMAIN_SCHEMA</span></span>|<span data-ttu-id="7c0dd-402">String</span><span class="sxs-lookup"><span data-stu-id="7c0dd-402">String</span></span>|  
|<span data-ttu-id="7c0dd-403">DOMAIN_NAME</span><span class="sxs-lookup"><span data-stu-id="7c0dd-403">DOMAIN_NAME</span></span>|<span data-ttu-id="7c0dd-404">String</span><span class="sxs-lookup"><span data-stu-id="7c0dd-404">String</span></span>|  
|<span data-ttu-id="7c0dd-405">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="7c0dd-405">DESCRIPTION</span></span>|<span data-ttu-id="7c0dd-406">String</span><span class="sxs-lookup"><span data-stu-id="7c0dd-406">String</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="7c0dd-407">Процедуры</span><span class="sxs-lookup"><span data-stu-id="7c0dd-407">Procedures</span></span>  
  
|<span data-ttu-id="7c0dd-408">ColumnName</span><span class="sxs-lookup"><span data-stu-id="7c0dd-408">ColumnName</span></span>|<span data-ttu-id="7c0dd-409">DataType</span><span class="sxs-lookup"><span data-stu-id="7c0dd-409">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="7c0dd-410">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="7c0dd-410">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="7c0dd-411">String</span><span class="sxs-lookup"><span data-stu-id="7c0dd-411">String</span></span>|  
|<span data-ttu-id="7c0dd-412">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="7c0dd-412">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="7c0dd-413">String</span><span class="sxs-lookup"><span data-stu-id="7c0dd-413">String</span></span>|  
|<span data-ttu-id="7c0dd-414">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="7c0dd-414">PROCEDURE_NAME</span></span>|<span data-ttu-id="7c0dd-415">String</span><span class="sxs-lookup"><span data-stu-id="7c0dd-415">String</span></span>|  
|<span data-ttu-id="7c0dd-416">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="7c0dd-416">PROCEDURE_TYPE</span></span>|<span data-ttu-id="7c0dd-417">Int16</span><span class="sxs-lookup"><span data-stu-id="7c0dd-417">Int16</span></span>|  
|<span data-ttu-id="7c0dd-418">PROCEDURE_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="7c0dd-418">PROCEDURE_DEFINITION</span></span>|<span data-ttu-id="7c0dd-419">String</span><span class="sxs-lookup"><span data-stu-id="7c0dd-419">String</span></span>|  
|<span data-ttu-id="7c0dd-420">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="7c0dd-420">DESCRIPTION</span></span>|<span data-ttu-id="7c0dd-421">String</span><span class="sxs-lookup"><span data-stu-id="7c0dd-421">String</span></span>|  
|<span data-ttu-id="7c0dd-422">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="7c0dd-422">DATE_CREATED</span></span>|<span data-ttu-id="7c0dd-423">DateTime</span><span class="sxs-lookup"><span data-stu-id="7c0dd-423">DateTime</span></span>|  
|<span data-ttu-id="7c0dd-424">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="7c0dd-424">DATE_MODIFIED</span></span>|<span data-ttu-id="7c0dd-425">DateTime</span><span class="sxs-lookup"><span data-stu-id="7c0dd-425">DateTime</span></span>|  
  
### <a name="procedurecolumns"></a><span data-ttu-id="7c0dd-426">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="7c0dd-426">ProcedureColumns</span></span>  
  
|<span data-ttu-id="7c0dd-427">ColumnName</span><span class="sxs-lookup"><span data-stu-id="7c0dd-427">ColumnName</span></span>|<span data-ttu-id="7c0dd-428">DataType</span><span class="sxs-lookup"><span data-stu-id="7c0dd-428">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="7c0dd-429">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="7c0dd-429">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="7c0dd-430">String</span><span class="sxs-lookup"><span data-stu-id="7c0dd-430">String</span></span>|  
|<span data-ttu-id="7c0dd-431">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="7c0dd-431">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="7c0dd-432">String</span><span class="sxs-lookup"><span data-stu-id="7c0dd-432">String</span></span>|  
|<span data-ttu-id="7c0dd-433">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="7c0dd-433">PROCEDURE_NAME</span></span>|<span data-ttu-id="7c0dd-434">String</span><span class="sxs-lookup"><span data-stu-id="7c0dd-434">String</span></span>|  
|<span data-ttu-id="7c0dd-435">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="7c0dd-435">COLUMN_NAME</span></span>|<span data-ttu-id="7c0dd-436">String</span><span class="sxs-lookup"><span data-stu-id="7c0dd-436">String</span></span>|  
|<span data-ttu-id="7c0dd-437">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="7c0dd-437">COLUMN_GUID</span></span>|<span data-ttu-id="7c0dd-438">Guid</span><span class="sxs-lookup"><span data-stu-id="7c0dd-438">Guid</span></span>|  
|<span data-ttu-id="7c0dd-439">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="7c0dd-439">COLUMN_PROPID</span></span>|<span data-ttu-id="7c0dd-440">Int64</span><span class="sxs-lookup"><span data-stu-id="7c0dd-440">Int64</span></span>|  
|<span data-ttu-id="7c0dd-441">ROWSET_NUMBER</span><span class="sxs-lookup"><span data-stu-id="7c0dd-441">ROWSET_NUMBER</span></span>|<span data-ttu-id="7c0dd-442">Int64</span><span class="sxs-lookup"><span data-stu-id="7c0dd-442">Int64</span></span>|  
|<span data-ttu-id="7c0dd-443">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="7c0dd-443">ORDINAL_POSITION</span></span>|<span data-ttu-id="7c0dd-444">Int64</span><span class="sxs-lookup"><span data-stu-id="7c0dd-444">Int64</span></span>|  
|<span data-ttu-id="7c0dd-445">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="7c0dd-445">IS_NULLABLE</span></span>|<span data-ttu-id="7c0dd-446">логический</span><span class="sxs-lookup"><span data-stu-id="7c0dd-446">Boolean</span></span>|  
|<span data-ttu-id="7c0dd-447">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="7c0dd-447">DATA_TYPE</span></span>|<span data-ttu-id="7c0dd-448">Int32</span><span class="sxs-lookup"><span data-stu-id="7c0dd-448">Int32</span></span>|  
|<span data-ttu-id="7c0dd-449">TYPE_GUID</span><span class="sxs-lookup"><span data-stu-id="7c0dd-449">TYPE_GUID</span></span>|<span data-ttu-id="7c0dd-450">Guid</span><span class="sxs-lookup"><span data-stu-id="7c0dd-450">Guid</span></span>|  
|<span data-ttu-id="7c0dd-451">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="7c0dd-451">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="7c0dd-452">Int64</span><span class="sxs-lookup"><span data-stu-id="7c0dd-452">Int64</span></span>|  
|<span data-ttu-id="7c0dd-453">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="7c0dd-453">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="7c0dd-454">Int64</span><span class="sxs-lookup"><span data-stu-id="7c0dd-454">Int64</span></span>|  
|<span data-ttu-id="7c0dd-455">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="7c0dd-455">NUMERIC_PRECISION</span></span>|<span data-ttu-id="7c0dd-456">Int32</span><span class="sxs-lookup"><span data-stu-id="7c0dd-456">Int32</span></span>|  
|<span data-ttu-id="7c0dd-457">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="7c0dd-457">NUMERIC_SCALE</span></span>|<span data-ttu-id="7c0dd-458">Int16</span><span class="sxs-lookup"><span data-stu-id="7c0dd-458">Int16</span></span>|  
|<span data-ttu-id="7c0dd-459">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="7c0dd-459">DESCRIPTION</span></span>|<span data-ttu-id="7c0dd-460">String</span><span class="sxs-lookup"><span data-stu-id="7c0dd-460">String</span></span>|  
|<span data-ttu-id="7c0dd-461">OVERLOAD</span><span class="sxs-lookup"><span data-stu-id="7c0dd-461">OVERLOAD</span></span>|<span data-ttu-id="7c0dd-462">Int16</span><span class="sxs-lookup"><span data-stu-id="7c0dd-462">Int16</span></span>|  
  
### <a name="views"></a><span data-ttu-id="7c0dd-463">Представления</span><span class="sxs-lookup"><span data-stu-id="7c0dd-463">Views</span></span>  
  
|<span data-ttu-id="7c0dd-464">ColumnName</span><span class="sxs-lookup"><span data-stu-id="7c0dd-464">ColumnName</span></span>|<span data-ttu-id="7c0dd-465">DataType</span><span class="sxs-lookup"><span data-stu-id="7c0dd-465">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="7c0dd-466">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="7c0dd-466">TABLE_CATALOG</span></span>|<span data-ttu-id="7c0dd-467">String</span><span class="sxs-lookup"><span data-stu-id="7c0dd-467">String</span></span>|  
|<span data-ttu-id="7c0dd-468">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="7c0dd-468">TABLE_SCHEMA</span></span>|<span data-ttu-id="7c0dd-469">String</span><span class="sxs-lookup"><span data-stu-id="7c0dd-469">String</span></span>|  
|<span data-ttu-id="7c0dd-470">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="7c0dd-470">TABLE_NAME</span></span>|<span data-ttu-id="7c0dd-471">String</span><span class="sxs-lookup"><span data-stu-id="7c0dd-471">String</span></span>|  
|<span data-ttu-id="7c0dd-472">VIEW_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="7c0dd-472">VIEW_DEFINITION</span></span>|<span data-ttu-id="7c0dd-473">String</span><span class="sxs-lookup"><span data-stu-id="7c0dd-473">String</span></span>|  
|<span data-ttu-id="7c0dd-474">CHECK_OPTION</span><span class="sxs-lookup"><span data-stu-id="7c0dd-474">CHECK_OPTION</span></span>|<span data-ttu-id="7c0dd-475">логический</span><span class="sxs-lookup"><span data-stu-id="7c0dd-475">Boolean</span></span>|  
|<span data-ttu-id="7c0dd-476">IS_UPDATABLE</span><span class="sxs-lookup"><span data-stu-id="7c0dd-476">IS_UPDATABLE</span></span>|<span data-ttu-id="7c0dd-477">логический</span><span class="sxs-lookup"><span data-stu-id="7c0dd-477">Boolean</span></span>|  
|<span data-ttu-id="7c0dd-478">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="7c0dd-478">DESCRIPTION</span></span>|<span data-ttu-id="7c0dd-479">String</span><span class="sxs-lookup"><span data-stu-id="7c0dd-479">String</span></span>|  
|<span data-ttu-id="7c0dd-480">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="7c0dd-480">DATE_CREATED</span></span>|<span data-ttu-id="7c0dd-481">DateTime</span><span class="sxs-lookup"><span data-stu-id="7c0dd-481">DateTime</span></span>|  
|<span data-ttu-id="7c0dd-482">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="7c0dd-482">DATE_MODIFIED</span></span>|<span data-ttu-id="7c0dd-483">DateTime</span><span class="sxs-lookup"><span data-stu-id="7c0dd-483">DateTime</span></span>|  
  
### <a name="indexes"></a><span data-ttu-id="7c0dd-484">Индексы</span><span class="sxs-lookup"><span data-stu-id="7c0dd-484">Indexes</span></span>  
  
|<span data-ttu-id="7c0dd-485">ColumnName</span><span class="sxs-lookup"><span data-stu-id="7c0dd-485">ColumnName</span></span>|<span data-ttu-id="7c0dd-486">DataType</span><span class="sxs-lookup"><span data-stu-id="7c0dd-486">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="7c0dd-487">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="7c0dd-487">TABLE_CATALOG</span></span>|<span data-ttu-id="7c0dd-488">String</span><span class="sxs-lookup"><span data-stu-id="7c0dd-488">String</span></span>|  
|<span data-ttu-id="7c0dd-489">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="7c0dd-489">TABLE_SCHEMA</span></span>|<span data-ttu-id="7c0dd-490">String</span><span class="sxs-lookup"><span data-stu-id="7c0dd-490">String</span></span>|  
|<span data-ttu-id="7c0dd-491">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="7c0dd-491">TABLE_NAME</span></span>|<span data-ttu-id="7c0dd-492">String</span><span class="sxs-lookup"><span data-stu-id="7c0dd-492">String</span></span>|  
|<span data-ttu-id="7c0dd-493">INDEX_CATALOG</span><span class="sxs-lookup"><span data-stu-id="7c0dd-493">INDEX_CATALOG</span></span>|<span data-ttu-id="7c0dd-494">String</span><span class="sxs-lookup"><span data-stu-id="7c0dd-494">String</span></span>|  
|<span data-ttu-id="7c0dd-495">INDEX_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="7c0dd-495">INDEX_SCHEMA</span></span>|<span data-ttu-id="7c0dd-496">String</span><span class="sxs-lookup"><span data-stu-id="7c0dd-496">String</span></span>|  
|<span data-ttu-id="7c0dd-497">INDEX_NAME</span><span class="sxs-lookup"><span data-stu-id="7c0dd-497">INDEX_NAME</span></span>|<span data-ttu-id="7c0dd-498">String</span><span class="sxs-lookup"><span data-stu-id="7c0dd-498">String</span></span>|  
|<span data-ttu-id="7c0dd-499">PRIMARY_KEY</span><span class="sxs-lookup"><span data-stu-id="7c0dd-499">PRIMARY_KEY</span></span>|<span data-ttu-id="7c0dd-500">логический</span><span class="sxs-lookup"><span data-stu-id="7c0dd-500">Boolean</span></span>|  
|<span data-ttu-id="7c0dd-501">UNIQUE</span><span class="sxs-lookup"><span data-stu-id="7c0dd-501">UNIQUE</span></span>|<span data-ttu-id="7c0dd-502">логический</span><span class="sxs-lookup"><span data-stu-id="7c0dd-502">Boolean</span></span>|  
|<span data-ttu-id="7c0dd-503">CLUSTERED</span><span class="sxs-lookup"><span data-stu-id="7c0dd-503">CLUSTERED</span></span>|<span data-ttu-id="7c0dd-504">логический</span><span class="sxs-lookup"><span data-stu-id="7c0dd-504">Boolean</span></span>|  
|<span data-ttu-id="7c0dd-505">ТИП</span><span class="sxs-lookup"><span data-stu-id="7c0dd-505">TYPE</span></span>|<span data-ttu-id="7c0dd-506">Int32</span><span class="sxs-lookup"><span data-stu-id="7c0dd-506">Int32</span></span>|  
|<span data-ttu-id="7c0dd-507">FILL_FACTOR</span><span class="sxs-lookup"><span data-stu-id="7c0dd-507">FILL_FACTOR</span></span>|<span data-ttu-id="7c0dd-508">Int32</span><span class="sxs-lookup"><span data-stu-id="7c0dd-508">Int32</span></span>|  
|<span data-ttu-id="7c0dd-509">INITIAL_SIZE</span><span class="sxs-lookup"><span data-stu-id="7c0dd-509">INITIAL_SIZE</span></span>|<span data-ttu-id="7c0dd-510">Int32</span><span class="sxs-lookup"><span data-stu-id="7c0dd-510">Int32</span></span>|  
|<span data-ttu-id="7c0dd-511">NULLS</span><span class="sxs-lookup"><span data-stu-id="7c0dd-511">NULLS</span></span>|<span data-ttu-id="7c0dd-512">Int32</span><span class="sxs-lookup"><span data-stu-id="7c0dd-512">Int32</span></span>|  
|<span data-ttu-id="7c0dd-513">SORT_BOOKMARKS</span><span class="sxs-lookup"><span data-stu-id="7c0dd-513">SORT_BOOKMARKS</span></span>|<span data-ttu-id="7c0dd-514">логический</span><span class="sxs-lookup"><span data-stu-id="7c0dd-514">Boolean</span></span>|  
|<span data-ttu-id="7c0dd-515">AUTO_UPDATE</span><span class="sxs-lookup"><span data-stu-id="7c0dd-515">AUTO_UPDATE</span></span>|<span data-ttu-id="7c0dd-516">логический</span><span class="sxs-lookup"><span data-stu-id="7c0dd-516">Boolean</span></span>|  
|<span data-ttu-id="7c0dd-517">NULL_COLLATION</span><span class="sxs-lookup"><span data-stu-id="7c0dd-517">NULL_COLLATION</span></span>|<span data-ttu-id="7c0dd-518">Int32</span><span class="sxs-lookup"><span data-stu-id="7c0dd-518">Int32</span></span>|  
|<span data-ttu-id="7c0dd-519">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="7c0dd-519">ORDINAL_POSITION</span></span>|<span data-ttu-id="7c0dd-520">Int64</span><span class="sxs-lookup"><span data-stu-id="7c0dd-520">Int64</span></span>|  
|<span data-ttu-id="7c0dd-521">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="7c0dd-521">COLUMN_NAME</span></span>|<span data-ttu-id="7c0dd-522">String</span><span class="sxs-lookup"><span data-stu-id="7c0dd-522">String</span></span>|  
|<span data-ttu-id="7c0dd-523">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="7c0dd-523">COLUMN_GUID</span></span>|<span data-ttu-id="7c0dd-524">Guid</span><span class="sxs-lookup"><span data-stu-id="7c0dd-524">Guid</span></span>|  
|<span data-ttu-id="7c0dd-525">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="7c0dd-525">COLUMN_PROPID</span></span>|<span data-ttu-id="7c0dd-526">Int64</span><span class="sxs-lookup"><span data-stu-id="7c0dd-526">Int64</span></span>|  
|<span data-ttu-id="7c0dd-527">COLLATION</span><span class="sxs-lookup"><span data-stu-id="7c0dd-527">COLLATION</span></span>|<span data-ttu-id="7c0dd-528">Int16</span><span class="sxs-lookup"><span data-stu-id="7c0dd-528">Int16</span></span>|  
|<span data-ttu-id="7c0dd-529">CARDINALITY</span><span class="sxs-lookup"><span data-stu-id="7c0dd-529">CARDINALITY</span></span>|<span data-ttu-id="7c0dd-530">Decimal</span><span class="sxs-lookup"><span data-stu-id="7c0dd-530">Decimal</span></span>|  
|<span data-ttu-id="7c0dd-531">PAGES</span><span class="sxs-lookup"><span data-stu-id="7c0dd-531">PAGES</span></span>|<span data-ttu-id="7c0dd-532">Int32</span><span class="sxs-lookup"><span data-stu-id="7c0dd-532">Int32</span></span>|  
|<span data-ttu-id="7c0dd-533">FILTER_CONDITION</span><span class="sxs-lookup"><span data-stu-id="7c0dd-533">FILTER_CONDITION</span></span>|<span data-ttu-id="7c0dd-534">String</span><span class="sxs-lookup"><span data-stu-id="7c0dd-534">String</span></span>|  
|<span data-ttu-id="7c0dd-535">INTEGRATED</span><span class="sxs-lookup"><span data-stu-id="7c0dd-535">INTEGRATED</span></span>|<span data-ttu-id="7c0dd-536">логический</span><span class="sxs-lookup"><span data-stu-id="7c0dd-536">Boolean</span></span>|  
  
## <a name="microsoft-jet-ole-db-provider"></a><span data-ttu-id="7c0dd-537">Поставщик OLE DB для Microsoft Jet</span><span class="sxs-lookup"><span data-stu-id="7c0dd-537">Microsoft Jet OLE DB Provider</span></span>  
 <span data-ttu-id="7c0dd-538">Драйвер OLE DB для Jet (Майкрософт) поддерживает следующие специальные коллекции схем в дополнение к общим коллекциям.</span><span class="sxs-lookup"><span data-stu-id="7c0dd-538">The Microsoft Jet OLE DB Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
- <span data-ttu-id="7c0dd-539">Таблицы</span><span class="sxs-lookup"><span data-stu-id="7c0dd-539">Tables</span></span>  
  
- <span data-ttu-id="7c0dd-540">Столбцы</span><span class="sxs-lookup"><span data-stu-id="7c0dd-540">Columns</span></span>  
  
- <span data-ttu-id="7c0dd-541">Процедуры</span><span class="sxs-lookup"><span data-stu-id="7c0dd-541">Procedures</span></span>  
  
- <span data-ttu-id="7c0dd-542">Представления</span><span class="sxs-lookup"><span data-stu-id="7c0dd-542">Views</span></span>  
  
- <span data-ttu-id="7c0dd-543">Индексы</span><span class="sxs-lookup"><span data-stu-id="7c0dd-543">Indexes</span></span>  
  
### <a name="tables"></a><span data-ttu-id="7c0dd-544">Таблицы</span><span class="sxs-lookup"><span data-stu-id="7c0dd-544">Tables</span></span>  
  
|<span data-ttu-id="7c0dd-545">ColumnName</span><span class="sxs-lookup"><span data-stu-id="7c0dd-545">ColumnName</span></span>|<span data-ttu-id="7c0dd-546">DataType</span><span class="sxs-lookup"><span data-stu-id="7c0dd-546">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="7c0dd-547">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="7c0dd-547">TABLE_CATALOG</span></span>|<span data-ttu-id="7c0dd-548">String</span><span class="sxs-lookup"><span data-stu-id="7c0dd-548">String</span></span>|  
|<span data-ttu-id="7c0dd-549">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="7c0dd-549">TABLE_SCHEMA</span></span>|<span data-ttu-id="7c0dd-550">String</span><span class="sxs-lookup"><span data-stu-id="7c0dd-550">String</span></span>|  
|<span data-ttu-id="7c0dd-551">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="7c0dd-551">TABLE_NAME</span></span>|<span data-ttu-id="7c0dd-552">String</span><span class="sxs-lookup"><span data-stu-id="7c0dd-552">String</span></span>|  
|<span data-ttu-id="7c0dd-553">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="7c0dd-553">TABLE_TYPE</span></span>|<span data-ttu-id="7c0dd-554">String</span><span class="sxs-lookup"><span data-stu-id="7c0dd-554">String</span></span>|  
|<span data-ttu-id="7c0dd-555">TABLE_GUID</span><span class="sxs-lookup"><span data-stu-id="7c0dd-555">TABLE_GUID</span></span>|<span data-ttu-id="7c0dd-556">Guid</span><span class="sxs-lookup"><span data-stu-id="7c0dd-556">Guid</span></span>|  
|<span data-ttu-id="7c0dd-557">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="7c0dd-557">DESCRIPTION</span></span>|<span data-ttu-id="7c0dd-558">String</span><span class="sxs-lookup"><span data-stu-id="7c0dd-558">String</span></span>|  
|<span data-ttu-id="7c0dd-559">TABLE_PROPID</span><span class="sxs-lookup"><span data-stu-id="7c0dd-559">TABLE_PROPID</span></span>|<span data-ttu-id="7c0dd-560">Int64</span><span class="sxs-lookup"><span data-stu-id="7c0dd-560">Int64</span></span>|  
|<span data-ttu-id="7c0dd-561">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="7c0dd-561">DATE_CREATED</span></span>|<span data-ttu-id="7c0dd-562">DateTime</span><span class="sxs-lookup"><span data-stu-id="7c0dd-562">DateTime</span></span>|  
|<span data-ttu-id="7c0dd-563">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="7c0dd-563">DATE_MODIFIED</span></span>|<span data-ttu-id="7c0dd-564">DateTime</span><span class="sxs-lookup"><span data-stu-id="7c0dd-564">DateTime</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="7c0dd-565">Столбцы</span><span class="sxs-lookup"><span data-stu-id="7c0dd-565">Columns</span></span>  
  
|<span data-ttu-id="7c0dd-566">ColumnName</span><span class="sxs-lookup"><span data-stu-id="7c0dd-566">ColumnName</span></span>|<span data-ttu-id="7c0dd-567">DataType</span><span class="sxs-lookup"><span data-stu-id="7c0dd-567">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="7c0dd-568">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="7c0dd-568">TABLE_CATALOG</span></span>|<span data-ttu-id="7c0dd-569">String</span><span class="sxs-lookup"><span data-stu-id="7c0dd-569">String</span></span>|  
|<span data-ttu-id="7c0dd-570">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="7c0dd-570">TABLE_SCHEMA</span></span>|<span data-ttu-id="7c0dd-571">String</span><span class="sxs-lookup"><span data-stu-id="7c0dd-571">String</span></span>|  
|<span data-ttu-id="7c0dd-572">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="7c0dd-572">TABLE_NAME</span></span>|<span data-ttu-id="7c0dd-573">String</span><span class="sxs-lookup"><span data-stu-id="7c0dd-573">String</span></span>|  
|<span data-ttu-id="7c0dd-574">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="7c0dd-574">COLUMN_NAME</span></span>|<span data-ttu-id="7c0dd-575">String</span><span class="sxs-lookup"><span data-stu-id="7c0dd-575">String</span></span>|  
|<span data-ttu-id="7c0dd-576">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="7c0dd-576">COLUMN_GUID</span></span>|<span data-ttu-id="7c0dd-577">Guid</span><span class="sxs-lookup"><span data-stu-id="7c0dd-577">Guid</span></span>|  
|<span data-ttu-id="7c0dd-578">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="7c0dd-578">COLUMN_PROPID</span></span>|<span data-ttu-id="7c0dd-579">Int64</span><span class="sxs-lookup"><span data-stu-id="7c0dd-579">Int64</span></span>|  
|<span data-ttu-id="7c0dd-580">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="7c0dd-580">ORDINAL_POSITION</span></span>|<span data-ttu-id="7c0dd-581">Int64</span><span class="sxs-lookup"><span data-stu-id="7c0dd-581">Int64</span></span>|  
|<span data-ttu-id="7c0dd-582">COLUMN_HASDEFAULT</span><span class="sxs-lookup"><span data-stu-id="7c0dd-582">COLUMN_HASDEFAULT</span></span>|<span data-ttu-id="7c0dd-583">логический</span><span class="sxs-lookup"><span data-stu-id="7c0dd-583">Boolean</span></span>|  
|<span data-ttu-id="7c0dd-584">COLUMN_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="7c0dd-584">COLUMN_DEFAULT</span></span>|<span data-ttu-id="7c0dd-585">String</span><span class="sxs-lookup"><span data-stu-id="7c0dd-585">String</span></span>|  
|<span data-ttu-id="7c0dd-586">COLUMN_FLAGS</span><span class="sxs-lookup"><span data-stu-id="7c0dd-586">COLUMN_FLAGS</span></span>|<span data-ttu-id="7c0dd-587">Int64</span><span class="sxs-lookup"><span data-stu-id="7c0dd-587">Int64</span></span>|  
|<span data-ttu-id="7c0dd-588">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="7c0dd-588">IS_NULLABLE</span></span>|<span data-ttu-id="7c0dd-589">логический</span><span class="sxs-lookup"><span data-stu-id="7c0dd-589">Boolean</span></span>|  
|<span data-ttu-id="7c0dd-590">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="7c0dd-590">DATA_TYPE</span></span>|<span data-ttu-id="7c0dd-591">Int32</span><span class="sxs-lookup"><span data-stu-id="7c0dd-591">Int32</span></span>|  
|<span data-ttu-id="7c0dd-592">TYPE_GUID</span><span class="sxs-lookup"><span data-stu-id="7c0dd-592">TYPE_GUID</span></span>|<span data-ttu-id="7c0dd-593">Guid</span><span class="sxs-lookup"><span data-stu-id="7c0dd-593">Guid</span></span>|  
|<span data-ttu-id="7c0dd-594">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="7c0dd-594">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="7c0dd-595">Int64</span><span class="sxs-lookup"><span data-stu-id="7c0dd-595">Int64</span></span>|  
|<span data-ttu-id="7c0dd-596">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="7c0dd-596">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="7c0dd-597">Int64</span><span class="sxs-lookup"><span data-stu-id="7c0dd-597">Int64</span></span>|  
|<span data-ttu-id="7c0dd-598">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="7c0dd-598">NUMERIC_PRECISION</span></span>|<span data-ttu-id="7c0dd-599">Int32</span><span class="sxs-lookup"><span data-stu-id="7c0dd-599">Int32</span></span>|  
|<span data-ttu-id="7c0dd-600">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="7c0dd-600">NUMERIC_SCALE</span></span>|<span data-ttu-id="7c0dd-601">Int16</span><span class="sxs-lookup"><span data-stu-id="7c0dd-601">Int16</span></span>|  
|<span data-ttu-id="7c0dd-602">DATETIME_PRECISION</span><span class="sxs-lookup"><span data-stu-id="7c0dd-602">DATETIME_PRECISION</span></span>|<span data-ttu-id="7c0dd-603">Int64</span><span class="sxs-lookup"><span data-stu-id="7c0dd-603">Int64</span></span>|  
|<span data-ttu-id="7c0dd-604">CHARACTER_SET_CATALOG</span><span class="sxs-lookup"><span data-stu-id="7c0dd-604">CHARACTER_SET_CATALOG</span></span>|<span data-ttu-id="7c0dd-605">String</span><span class="sxs-lookup"><span data-stu-id="7c0dd-605">String</span></span>|  
|<span data-ttu-id="7c0dd-606">CHARACTER_SET_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="7c0dd-606">CHARACTER_SET_SCHEMA</span></span>|<span data-ttu-id="7c0dd-607">String</span><span class="sxs-lookup"><span data-stu-id="7c0dd-607">String</span></span>|  
|<span data-ttu-id="7c0dd-608">CHARACTER_SET_NAME</span><span class="sxs-lookup"><span data-stu-id="7c0dd-608">CHARACTER_SET_NAME</span></span>|<span data-ttu-id="7c0dd-609">String</span><span class="sxs-lookup"><span data-stu-id="7c0dd-609">String</span></span>|  
|<span data-ttu-id="7c0dd-610">COLLATION_CATALOG</span><span class="sxs-lookup"><span data-stu-id="7c0dd-610">COLLATION_CATALOG</span></span>|<span data-ttu-id="7c0dd-611">String</span><span class="sxs-lookup"><span data-stu-id="7c0dd-611">String</span></span>|  
|<span data-ttu-id="7c0dd-612">COLLATION_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="7c0dd-612">COLLATION_SCHEMA</span></span>|<span data-ttu-id="7c0dd-613">String</span><span class="sxs-lookup"><span data-stu-id="7c0dd-613">String</span></span>|  
|<span data-ttu-id="7c0dd-614">COLLATION_NAME</span><span class="sxs-lookup"><span data-stu-id="7c0dd-614">COLLATION_NAME</span></span>|<span data-ttu-id="7c0dd-615">String</span><span class="sxs-lookup"><span data-stu-id="7c0dd-615">String</span></span>|  
|<span data-ttu-id="7c0dd-616">DOMAIN_CATALOG</span><span class="sxs-lookup"><span data-stu-id="7c0dd-616">DOMAIN_CATALOG</span></span>|<span data-ttu-id="7c0dd-617">String</span><span class="sxs-lookup"><span data-stu-id="7c0dd-617">String</span></span>|  
|<span data-ttu-id="7c0dd-618">DOMAIN_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="7c0dd-618">DOMAIN_SCHEMA</span></span>|<span data-ttu-id="7c0dd-619">String</span><span class="sxs-lookup"><span data-stu-id="7c0dd-619">String</span></span>|  
|<span data-ttu-id="7c0dd-620">DOMAIN_NAME</span><span class="sxs-lookup"><span data-stu-id="7c0dd-620">DOMAIN_NAME</span></span>|<span data-ttu-id="7c0dd-621">String</span><span class="sxs-lookup"><span data-stu-id="7c0dd-621">String</span></span>|  
|<span data-ttu-id="7c0dd-622">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="7c0dd-622">DESCRIPTION</span></span>|<span data-ttu-id="7c0dd-623">String</span><span class="sxs-lookup"><span data-stu-id="7c0dd-623">String</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="7c0dd-624">Процедуры</span><span class="sxs-lookup"><span data-stu-id="7c0dd-624">Procedures</span></span>  
  
|<span data-ttu-id="7c0dd-625">ColumnName</span><span class="sxs-lookup"><span data-stu-id="7c0dd-625">ColumnName</span></span>|<span data-ttu-id="7c0dd-626">DataType</span><span class="sxs-lookup"><span data-stu-id="7c0dd-626">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="7c0dd-627">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="7c0dd-627">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="7c0dd-628">String</span><span class="sxs-lookup"><span data-stu-id="7c0dd-628">String</span></span>|  
|<span data-ttu-id="7c0dd-629">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="7c0dd-629">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="7c0dd-630">String</span><span class="sxs-lookup"><span data-stu-id="7c0dd-630">String</span></span>|  
|<span data-ttu-id="7c0dd-631">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="7c0dd-631">PROCEDURE_NAME</span></span>|<span data-ttu-id="7c0dd-632">String</span><span class="sxs-lookup"><span data-stu-id="7c0dd-632">String</span></span>|  
|<span data-ttu-id="7c0dd-633">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="7c0dd-633">PROCEDURE_TYPE</span></span>|<span data-ttu-id="7c0dd-634">Int16</span><span class="sxs-lookup"><span data-stu-id="7c0dd-634">Int16</span></span>|  
|<span data-ttu-id="7c0dd-635">PROCEDURE_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="7c0dd-635">PROCEDURE_DEFINITION</span></span>|<span data-ttu-id="7c0dd-636">String</span><span class="sxs-lookup"><span data-stu-id="7c0dd-636">String</span></span>|  
|<span data-ttu-id="7c0dd-637">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="7c0dd-637">DESCRIPTION</span></span>|<span data-ttu-id="7c0dd-638">String</span><span class="sxs-lookup"><span data-stu-id="7c0dd-638">String</span></span>|  
|<span data-ttu-id="7c0dd-639">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="7c0dd-639">DATE_CREATED</span></span>|<span data-ttu-id="7c0dd-640">DateTime</span><span class="sxs-lookup"><span data-stu-id="7c0dd-640">DateTime</span></span>|  
|<span data-ttu-id="7c0dd-641">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="7c0dd-641">DATE_MODIFIED</span></span>|<span data-ttu-id="7c0dd-642">DateTime</span><span class="sxs-lookup"><span data-stu-id="7c0dd-642">DateTime</span></span>|  
  
### <a name="views"></a><span data-ttu-id="7c0dd-643">Представления</span><span class="sxs-lookup"><span data-stu-id="7c0dd-643">Views</span></span>  
  
|<span data-ttu-id="7c0dd-644">ColumnName</span><span class="sxs-lookup"><span data-stu-id="7c0dd-644">ColumnName</span></span>|<span data-ttu-id="7c0dd-645">DataType</span><span class="sxs-lookup"><span data-stu-id="7c0dd-645">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="7c0dd-646">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="7c0dd-646">TABLE_CATALOG</span></span>|<span data-ttu-id="7c0dd-647">String</span><span class="sxs-lookup"><span data-stu-id="7c0dd-647">String</span></span>|  
|<span data-ttu-id="7c0dd-648">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="7c0dd-648">TABLE_SCHEMA</span></span>|<span data-ttu-id="7c0dd-649">String</span><span class="sxs-lookup"><span data-stu-id="7c0dd-649">String</span></span>|  
|<span data-ttu-id="7c0dd-650">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="7c0dd-650">TABLE_NAME</span></span>|<span data-ttu-id="7c0dd-651">String</span><span class="sxs-lookup"><span data-stu-id="7c0dd-651">String</span></span>|  
|<span data-ttu-id="7c0dd-652">VIEW_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="7c0dd-652">VIEW_DEFINITION</span></span>|<span data-ttu-id="7c0dd-653">String</span><span class="sxs-lookup"><span data-stu-id="7c0dd-653">String</span></span>|  
|<span data-ttu-id="7c0dd-654">CHECK_OPTION</span><span class="sxs-lookup"><span data-stu-id="7c0dd-654">CHECK_OPTION</span></span>|<span data-ttu-id="7c0dd-655">логический</span><span class="sxs-lookup"><span data-stu-id="7c0dd-655">Boolean</span></span>|  
|<span data-ttu-id="7c0dd-656">IS_UPDATABLE</span><span class="sxs-lookup"><span data-stu-id="7c0dd-656">IS_UPDATABLE</span></span>|<span data-ttu-id="7c0dd-657">логический</span><span class="sxs-lookup"><span data-stu-id="7c0dd-657">Boolean</span></span>|  
|<span data-ttu-id="7c0dd-658">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="7c0dd-658">DESCRIPTION</span></span>|<span data-ttu-id="7c0dd-659">String</span><span class="sxs-lookup"><span data-stu-id="7c0dd-659">String</span></span>|  
|<span data-ttu-id="7c0dd-660">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="7c0dd-660">DATE_CREATED</span></span>|<span data-ttu-id="7c0dd-661">DateTime</span><span class="sxs-lookup"><span data-stu-id="7c0dd-661">DateTime</span></span>|  
|<span data-ttu-id="7c0dd-662">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="7c0dd-662">DATE_MODIFIED</span></span>|<span data-ttu-id="7c0dd-663">DateTime</span><span class="sxs-lookup"><span data-stu-id="7c0dd-663">DateTime</span></span>|  
  
### <a name="indexes"></a><span data-ttu-id="7c0dd-664">Индексы</span><span class="sxs-lookup"><span data-stu-id="7c0dd-664">Indexes</span></span>  
  
|<span data-ttu-id="7c0dd-665">ColumnName</span><span class="sxs-lookup"><span data-stu-id="7c0dd-665">ColumnName</span></span>|<span data-ttu-id="7c0dd-666">DataType</span><span class="sxs-lookup"><span data-stu-id="7c0dd-666">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="7c0dd-667">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="7c0dd-667">TABLE_CATALOG</span></span>|<span data-ttu-id="7c0dd-668">String</span><span class="sxs-lookup"><span data-stu-id="7c0dd-668">String</span></span>|  
|<span data-ttu-id="7c0dd-669">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="7c0dd-669">TABLE_SCHEMA</span></span>|<span data-ttu-id="7c0dd-670">String</span><span class="sxs-lookup"><span data-stu-id="7c0dd-670">String</span></span>|  
|<span data-ttu-id="7c0dd-671">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="7c0dd-671">TABLE_NAME</span></span>|<span data-ttu-id="7c0dd-672">String</span><span class="sxs-lookup"><span data-stu-id="7c0dd-672">String</span></span>|  
|<span data-ttu-id="7c0dd-673">INDEX_CATALOG</span><span class="sxs-lookup"><span data-stu-id="7c0dd-673">INDEX_CATALOG</span></span>|<span data-ttu-id="7c0dd-674">String</span><span class="sxs-lookup"><span data-stu-id="7c0dd-674">String</span></span>|  
|<span data-ttu-id="7c0dd-675">INDEX_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="7c0dd-675">INDEX_SCHEMA</span></span>|<span data-ttu-id="7c0dd-676">String</span><span class="sxs-lookup"><span data-stu-id="7c0dd-676">String</span></span>|  
|<span data-ttu-id="7c0dd-677">INDEX_NAME</span><span class="sxs-lookup"><span data-stu-id="7c0dd-677">INDEX_NAME</span></span>|<span data-ttu-id="7c0dd-678">String</span><span class="sxs-lookup"><span data-stu-id="7c0dd-678">String</span></span>|  
|<span data-ttu-id="7c0dd-679">PRIMARY_KEY</span><span class="sxs-lookup"><span data-stu-id="7c0dd-679">PRIMARY_KEY</span></span>|<span data-ttu-id="7c0dd-680">логический</span><span class="sxs-lookup"><span data-stu-id="7c0dd-680">Boolean</span></span>|  
|<span data-ttu-id="7c0dd-681">UNIQUE</span><span class="sxs-lookup"><span data-stu-id="7c0dd-681">UNIQUE</span></span>|<span data-ttu-id="7c0dd-682">логический</span><span class="sxs-lookup"><span data-stu-id="7c0dd-682">Boolean</span></span>|  
|<span data-ttu-id="7c0dd-683">CLUSTERED</span><span class="sxs-lookup"><span data-stu-id="7c0dd-683">CLUSTERED</span></span>|<span data-ttu-id="7c0dd-684">логический</span><span class="sxs-lookup"><span data-stu-id="7c0dd-684">Boolean</span></span>|  
|<span data-ttu-id="7c0dd-685">ТИП</span><span class="sxs-lookup"><span data-stu-id="7c0dd-685">TYPE</span></span>|<span data-ttu-id="7c0dd-686">Int32</span><span class="sxs-lookup"><span data-stu-id="7c0dd-686">Int32</span></span>|  
|<span data-ttu-id="7c0dd-687">FILL_FACTOR</span><span class="sxs-lookup"><span data-stu-id="7c0dd-687">FILL_FACTOR</span></span>|<span data-ttu-id="7c0dd-688">Int32</span><span class="sxs-lookup"><span data-stu-id="7c0dd-688">Int32</span></span>|  
|<span data-ttu-id="7c0dd-689">INITIAL_SIZE</span><span class="sxs-lookup"><span data-stu-id="7c0dd-689">INITIAL_SIZE</span></span>|<span data-ttu-id="7c0dd-690">Int32</span><span class="sxs-lookup"><span data-stu-id="7c0dd-690">Int32</span></span>|  
|<span data-ttu-id="7c0dd-691">NULLS</span><span class="sxs-lookup"><span data-stu-id="7c0dd-691">NULLS</span></span>|<span data-ttu-id="7c0dd-692">Int32</span><span class="sxs-lookup"><span data-stu-id="7c0dd-692">Int32</span></span>|  
|<span data-ttu-id="7c0dd-693">SORT_BOOKMARKS</span><span class="sxs-lookup"><span data-stu-id="7c0dd-693">SORT_BOOKMARKS</span></span>|<span data-ttu-id="7c0dd-694">логический</span><span class="sxs-lookup"><span data-stu-id="7c0dd-694">Boolean</span></span>|  
|<span data-ttu-id="7c0dd-695">AUTO_UPDATE</span><span class="sxs-lookup"><span data-stu-id="7c0dd-695">AUTO_UPDATE</span></span>|<span data-ttu-id="7c0dd-696">логический</span><span class="sxs-lookup"><span data-stu-id="7c0dd-696">Boolean</span></span>|  
|<span data-ttu-id="7c0dd-697">NULL_COLLATION</span><span class="sxs-lookup"><span data-stu-id="7c0dd-697">NULL_COLLATION</span></span>|<span data-ttu-id="7c0dd-698">Int32</span><span class="sxs-lookup"><span data-stu-id="7c0dd-698">Int32</span></span>|  
|<span data-ttu-id="7c0dd-699">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="7c0dd-699">ORDINAL_POSITION</span></span>|<span data-ttu-id="7c0dd-700">Int64</span><span class="sxs-lookup"><span data-stu-id="7c0dd-700">Int64</span></span>|  
|<span data-ttu-id="7c0dd-701">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="7c0dd-701">COLUMN_NAME</span></span>|<span data-ttu-id="7c0dd-702">String</span><span class="sxs-lookup"><span data-stu-id="7c0dd-702">String</span></span>|  
|<span data-ttu-id="7c0dd-703">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="7c0dd-703">COLUMN_GUID</span></span>|<span data-ttu-id="7c0dd-704">Guid</span><span class="sxs-lookup"><span data-stu-id="7c0dd-704">Guid</span></span>|  
|<span data-ttu-id="7c0dd-705">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="7c0dd-705">COLUMN_PROPID</span></span>|<span data-ttu-id="7c0dd-706">Int64</span><span class="sxs-lookup"><span data-stu-id="7c0dd-706">Int64</span></span>|  
|<span data-ttu-id="7c0dd-707">COLLATION</span><span class="sxs-lookup"><span data-stu-id="7c0dd-707">COLLATION</span></span>|<span data-ttu-id="7c0dd-708">Int16</span><span class="sxs-lookup"><span data-stu-id="7c0dd-708">Int16</span></span>|  
|<span data-ttu-id="7c0dd-709">CARDINALITY</span><span class="sxs-lookup"><span data-stu-id="7c0dd-709">CARDINALITY</span></span>|<span data-ttu-id="7c0dd-710">Decimal</span><span class="sxs-lookup"><span data-stu-id="7c0dd-710">Decimal</span></span>|  
|<span data-ttu-id="7c0dd-711">PAGES</span><span class="sxs-lookup"><span data-stu-id="7c0dd-711">PAGES</span></span>|<span data-ttu-id="7c0dd-712">Int32</span><span class="sxs-lookup"><span data-stu-id="7c0dd-712">Int32</span></span>|  
|<span data-ttu-id="7c0dd-713">FILTER_CONDITION</span><span class="sxs-lookup"><span data-stu-id="7c0dd-713">FILTER_CONDITION</span></span>|<span data-ttu-id="7c0dd-714">String</span><span class="sxs-lookup"><span data-stu-id="7c0dd-714">String</span></span>|  
|<span data-ttu-id="7c0dd-715">INTEGRATED</span><span class="sxs-lookup"><span data-stu-id="7c0dd-715">INTEGRATED</span></span>|<span data-ttu-id="7c0dd-716">логический</span><span class="sxs-lookup"><span data-stu-id="7c0dd-716">Boolean</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="7c0dd-717">См. также</span><span class="sxs-lookup"><span data-stu-id="7c0dd-717">See also</span></span>

- [<span data-ttu-id="7c0dd-718">Общие сведения об ADO.NET</span><span class="sxs-lookup"><span data-stu-id="7c0dd-718">ADO.NET Overview</span></span>](ado-net-overview.md)
