# Copyright Amazon.com, Inc. or its affiliates. All Rights Reserved.
# SPDX-License-Identifier: Apache-2.0.

###########
include ../Makefile.aws_byte_buf

MAX_BUFFER_SIZE=40

# This bound allows us to reach 100% coverage rate
UNWINDSET += memset_impl.0:$(shell echo $$(($(MAX_BUFFER_SIZE) + 1)))

CBMCFLAGS +=

HARNESS_ENTRY = aws_byte_buf_clean_up_harness
HARNESS_FILE = $(HARNESS_ENTRY).c

PROOF_SOURCES += $(HARNESS_FILE)
PROOF_SOURCES += $(PROOF_SOURCE)/make_common_data_structures.c
PROOF_SOURCES += $(PROOF_SOURCE)/proof_allocators.c

PROOF_SOURCES += $(PROOF_STUB)/error.c
PROOF_SOURCES += $(PROOF_STUB)/memset_override.c

PROJECT_SOURCES += $(SRCDIR)/source/byte_buf.c
PROJECT_SOURCES += $(SRCDIR)/source/common.c

###########

include ../Makefile.common
