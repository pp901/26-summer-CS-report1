# ===== 报告信息（与 main.tex 保持一致） =====
STUDENT_ID   := 24020007096
STUDENT_NAME := 彭湘莲
BASENAME     := $(STUDENT_ID)-$(STUDENT_NAME)-计算机系统综合实践I实验报告

LATEX        := xelatex
LATEXFLAGS   := -interaction=nonstopmode -halt-on-error

.PHONY: all clean distclean view

all: $(BASENAME).pdf

# latexmk 自动处理多轮编译（目录/引用）
$(BASENAME).pdf: main.tex assets/ouc-logo.png
	latexmk -xelatex $(LATEXFLAGS) main.tex
	cp -f main.pdf "$(BASENAME).pdf"
	@echo "已生成：$(BASENAME).pdf"

# 在 Windows (WSL) 下直接打开 PDF
view: $(BASENAME).pdf
	@command -v wslview >/dev/null 2>&1 && wslview "$(BASENAME).pdf" || xdg-open "$(BASENAME).pdf" 2>/dev/null || true

clean:
	latexmk -c || true
	rm -f main.pdf main.brf

distclean: clean
	rm -f "$(BASENAME).pdf"
