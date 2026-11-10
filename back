
-- ==========================================
-- BANCO DE DADOS: LISTA DE TAREFAS
-- ==========================================

-- 1. CRIAR TABELA

CREATE TABLE IF NOT EXISTS public.tarefas (
    id UUID PRIMARY KEY DEFAULT gen_random_uuid(),

    titulo VARCHAR(255) NOT NULL,

    descricao TEXT,

    concluida BOOLEAN NOT NULL DEFAULT FALSE,

    created_at TIMESTAMPTZ NOT NULL DEFAULT NOW()
);


-- ==========================================
-- 2. HABILITAR SEGURANÇA RLS
-- ==========================================

ALTER TABLE public.tarefas
ENABLE ROW LEVEL SECURITY;


-- ==========================================
-- 3. PERMISSÕES PARA USUÁRIO ANÔNIMO
-- ==========================================

GRANT USAGE ON SCHEMA public TO anon;

GRANT SELECT, INSERT, UPDATE, DELETE
ON public.tarefas
TO anon;


-- ==========================================
-- 4. REMOVER POLÍTICAS ANTIGAS
-- (PERMITE EXECUTAR O SCRIPT NOVAMENTE)
-- ==========================================

DROP POLICY IF EXISTS "Permitir listar tarefas"
ON public.tarefas;

DROP POLICY IF EXISTS "Permitir cadastrar tarefas"
ON public.tarefas;

DROP POLICY IF EXISTS "Permitir editar tarefas"
ON public.tarefas;

DROP POLICY IF EXISTS "Permitir excluir tarefas"
ON public.tarefas;


-- ==========================================
-- 5. CREATE - CADASTRAR
-- ==========================================

CREATE POLICY "Permitir cadastrar tarefas"

ON public.tarefas

FOR INSERT

TO anon

WITH CHECK (true);


-- ==========================================
-- 6. READ - CONSULTAR
-- ==========================================

CREATE POLICY "Permitir listar tarefas"

ON public.tarefas

FOR SELECT

TO anon

USING (true);


-- ==========================================
-- 7. UPDATE - EDITAR
-- ==========================================

CREATE POLICY "Permitir editar tarefas"

ON public.tarefas

FOR UPDATE

TO anon

USING (true)

WITH CHECK (true);


-- ==========================================
-- 8. DELETE - EXCLUIR
-- ==========================================

CREATE POLICY "Permitir excluir tarefas"

ON public.tarefas

FOR DELETE

TO anon

USING (true);


-- ==========================================
-- 9. TESTAR TABELA
-- ==========================================

SELECT * FROM public.tarefas;

