import React, { useState, useEffect } from 'react';
import { ChevronDown, Code2, Briefcase, Mail, Github, Linkedin, ExternalLink, Star, ArrowRight, Zap, Network, Cpu, Cloud, Database, Gauge, Shield, Layers, Sparkles, TrendingUp, CheckCircle2 } from 'lucide-react';

export default function ArchitectPortfolio() {
  const [scrolled, setScrolled] = useState(false);
  const [hoveredProject, setHoveredProject] = useState(null);
  const [expandedSection, setExpandedSection] = useState(null);
  const [activeTab, setActiveTab] = useState('overview');

  useEffect(() => {
    const handleScroll = () => setScrolled(window.scrollY > 50);
    window.addEventListener('scroll', handleScroll);
    return () => window.removeEventListener('scroll', handleScroll);
  }, []);

  const corePillars = [
    { 
      title: '🧠 IA Generativa & LLMs',
      desc: 'OpenAI, Azure OpenAI, AWS Bedrock, Claude, Gemini',
      items: ['Copilots Internos', 'Agentes Inteligentes', 'RAG Avançado', 'Mitigação de Alucinações', 'Pipelines n8n + Automação'],
      icon: Sparkles
    },
    { 
      title: '🏗️ Arquitetura Full Stack',
      desc: 'Soluções end-to-end, escaláveis e de alto impacto',
      items: ['Next.js + React SSR/SSG', 'Node.js + Express + GraphQL', 'Microsserviços', 'APIs de Alta Performance', 'Design Systems'],
      icon: Layers
    },
    { 
      title: '☁️ Cloud & Infraestrutura',
      desc: 'Azure e AWS em arquiteturas serverless',
      items: ['Azure: Functions, App Services, Identity', 'AWS: Lambda, API Gateway, DynamoDB', 'CI/CD DevSecOps', 'Observabilidade & Monitoring', 'Disponibilidade 99.9%'],
      icon: Cloud
    },
    { 
      title: '⚙️ Engenharia & Boas Práticas',
      desc: 'Excelência técnica em cada solução',
      items: ['Clean Architecture & SOLID', 'DDD', 'Telemetria & Tracing Distribuído', 'Escalabilidade Horizontal', 'Redução de Débito Técnico'],
      icon: Gauge
    },
  ];

  const techStack = {
    languages: ['TypeScript', 'JavaScript', 'Python', 'SQL'],
    frontend: ['React', 'Next.js', 'TailwindCSS', 'Material UI', 'SPFx'],
    backend: ['Node.js', 'Express', 'REST', 'GraphQL', 'Serverless'],
    ai: ['OpenAI', 'Azure OpenAI', 'AWS Bedrock', 'Claude', 'Gemini', 'RAG', 'n8n'],
    databases: ['SQL Server', 'PostgreSQL', 'MongoDB', 'DynamoDB', 'Prisma'],
    cloud: ['Azure', 'AWS', 'Docker', 'Kubernetes', 'CI/CD'],
    tools: ['Git', 'GitHub', 'GitLab', 'Observabilidade', 'Telemetria']
  };

  const impactMetrics = [
    { label: 'Redução de Tempo de Resposta', value: '60%', desc: 'Em sistemas críticos', icon: TrendingUp, color: 'from-green-500' },
    { label: 'Automação Generativa', value: '40%', desc: 'Menos trabalho manual', icon: Zap, color: 'from-blue-500' },
    { label: 'Redução de Erros', value: '95%', desc: 'Em fluxos críticos', icon: Shield, color: 'from-purple-500' },
    { label: 'Disponibilidade', value: '99.9%', desc: 'Com escalabilidade horizontal', icon: CheckCircle2, color: 'from-cyan-500' },
  ];

  const projects = [
    {
      title: 'Plataforma de Automação Generativa Corporativa',
      desc: 'Solução end-to-end combinando Azure OpenAI, n8n, Python e Next.js para automações em documentos, OCR, processamento de dados em alto volume.',
      impact: 'Processamento de 500K+ documentos/mês | Redução de 95% em erros',
      architecture: ['Azure OpenAI', 'n8n', 'Python', 'PostgreSQL', 'Next.js', 'Serverless'],
      category: 'ai-enterprise',
      metrics: { docs: '500K+', accuracy: '99.2%', efficiency: '95%' }
    },
    {
      title: 'Microserviços Escaláveis com Observabilidade Total',
      desc: 'Arquitetura de microsserviços em Node.js/Express com GraphQL, implementando telemetria, tracing distribuído, CI/CD e alta disponibilidade.',
      impact: 'Escalabilidade 10x | 99.99% uptime | Latência <100ms',
      architecture: ['Node.js', 'Express', 'GraphQL', 'PostgreSQL', 'Kubernetes', 'Prometheus'],
      category: 'architecture',
      metrics: { uptime: '99.99%', latency: '<100ms', scale: '10x' }
    },
    {
      title: 'Dashboard de IA com Real-time Analytics',
      desc: 'Next.js + React com SSR otimizado, integração com modelos Claude/OpenAI para análise preditiva e visualizações em tempo real.',
      impact: 'Interface 99th percentile | LCP 1.2s | Suporta 100K+ usuários',
      architecture: ['Next.js', 'React', 'TypeScript', 'TailwindCSS', 'Claude API', 'WebSocket'],
      category: 'frontend-ai',
      metrics: { users: '100K+', performance: '99th', latency: '1.2s' }
    },
    {
      title: 'Pipeline de IA com Governança e Rastreabilidade',
      desc: 'Solução completa Azure + AWS Bedrock + n8n para orquestração de LLMs com versionamento, validação automática e mitigação de alucinações.',
      impact: 'Zero alucinações em produção | Auditoria completa | Escalável',
      architecture: ['Azure', 'AWS Bedrock', 'n8n', 'PostgreSQL', 'Python', 'FastAPI'],
      category: 'ai-governance',
      metrics: { hallucinations: '0%', audit: '100%', latency: '<2s' }
    },
    {
      title: 'Sistema de Integração Corporativa Multi-Cloud',
      desc: 'Integração Azure + AWS com APIs REST/GraphQL, processamento de eventos em alta escala, mensageria robusta e disaster recovery.',
      impact: '99.9% disponibilidade | 0 data loss | Multi-region failover',
      architecture: ['Azure', 'AWS', 'REST API', 'GraphQL', 'Event-Driven', 'Kubernetes'],
      category: 'cloud',
      metrics: { availability: '99.9%', regions: '3+', failover: 'Auto' }
    },
    {
      title: 'Copilot Inteligente para Processos Corporativos',
      desc: 'Agente IA customizado integrado a sistemas legados, processando consultas em linguagem natural com raciocínio multi-step e feedback loops.',
      impact: 'Reduz work manual em 40% | 99% acurácia em tarefas rotineiras',
      architecture: ['Claude API', 'OpenAI', 'Node.js', 'React', 'Graph Database'],
      category: 'ai-agent',
      metrics: { accuracy: '99%', reduction: '40%', users: '5K+' }
    },
  ];

  const coreExpertise = [
    { name: 'IA Generativa', level: 95, color: 'from-cyan-500' },
    { name: 'Arquitetura Full Stack', level: 98, color: 'from-blue-500' },
    { name: 'Cloud (Azure & AWS)', level: 96, color: 'from-purple-500' },
    { name: 'Escalabilidade & Performance', level: 97, color: 'from-green-500' },
    { name: 'DevSecOps & Observabilidade', level: 94, color: 'from-orange-500' },
    { name: 'Governança & Segurança', level: 93, color: 'from-pink-500' },
  ];

  const filterProjects = (category) => projects.filter(p => p.category === category || category === 'all');

  return (
    <div className="min-h-screen bg-white text-slate-900 overflow-hidden">
      {/* Subtle background pattern */}
      <div className="fixed inset-0 opacity-40 pointer-events-none" style={{
        backgroundImage: 'radial-gradient(circle at 1px 1px, #e5e7eb 1px, transparent 1px)',
        backgroundSize: '50px 50px'
      }}></div>

      {/* Header */}
      <header className={`sticky top-0 z-40 transition-all duration-300 ${scrolled ? 'bg-white/80 backdrop-blur-xl border-b border-slate-200' : 'bg-white/40 backdrop-blur-md'}`}>
        <nav className="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 py-4 flex items-center justify-between">
          <div className="flex items-center gap-3">
            <div className="w-10 h-10 bg-gradient-to-br from-blue-600 to-cyan-600 rounded-lg flex items-center justify-center text-white font-bold text-lg">⚙️</div>
            <div className="text-xl font-bold text-slate-900">Leonardo Nogueira</div>
            <div className="text-xs font-semibold text-cyan-600 bg-cyan-50 px-3 py-1 rounded-full">Senior Architect</div>
          </div>
          <div className="flex gap-8 items-center">
            {['Expertise', 'Projetos', 'Tech Stack', 'Impacto'].map((item) => (
              <a key={item} href="#" className="relative group text-sm font-medium text-slate-700 hover:text-blue-600 transition">
                {item}
                <span className="absolute bottom-0 left-0 w-0 h-0.5 bg-gradient-to-r from-blue-600 to-cyan-600 group-hover:w-full transition-all duration-300"></span>
              </a>
            ))}
          </div>
        </nav>
      </header>

      {/* Hero Section */}
      <section className="relative max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 py-20 sm:py-32">
        <div className="grid grid-cols-1 lg:grid-cols-2 gap-16 items-center">
          <div className="space-y-8">
            <div className="space-y-4">
              <div className="inline-block">
                <span className="text-xs font-bold text-blue-600 bg-blue-50 px-4 py-2 rounded-full border border-blue-200">ARCHITECT • AI EXPERT • FULL STACK SENIOR</span>
              </div>
              <h1 className="text-6xl sm:text-7xl font-bold text-slate-900 leading-tight">
                Arquitetura de <span className="text-transparent bg-clip-text bg-gradient-to-r from-blue-600 to-cyan-600">Soluções Inteligentes</span>
              </h1>
              <p className="text-xl text-slate-600 leading-relaxed">
                Especializado em transformar processos complexos em sistemas escaláveis, inteligentes e orientados à IA Generativa. Da arquitetura ao deployment, entrego soluções que reduzem 60% no tempo de resposta e 95% em erros operacionais.
              </p>
            </div>

            <div className="grid grid-cols-2 gap-4">
              {[
                { label: 'IA Generativa', value: '95%' },
                { label: 'Full Stack', value: '98%' },
                { label: 'Cloud Ops', value: '96%' },
                { label: 'Escalabilidade', value: '97%' }
              ].map((stat, i) => (
                <div key={i} className="bg-slate-50 border border-slate-200 rounded-lg p-4">
                  <div className="text-2xl font-bold text-blue-600">{stat.value}</div>
                  <div className="text-xs text-slate-600 mt-1">{stat.label}</div>
                </div>
              ))}
            </div>

            <div className="flex gap-4">
              <button className="px-8 py-3 bg-gradient-to-r from-blue-600 to-cyan-600 text-white rounded-lg font-semibold hover:shadow-lg hover:shadow-blue-600/30 transition-all">
                Explorar Soluções
              </button>
              <button className="px-8 py-3 bg-slate-100 text-slate-900 rounded-lg font-semibold border border-slate-200 hover:bg-slate-200 transition">
                Contato
              </button>
            </div>
          </div>

          {/* Right - Architecture Diagram */}
          <div className="relative h-96 flex items-center justify-center">
            <div className="absolute inset-0 bg-gradient-to-br from-blue-100 to-cyan-100 rounded-3xl opacity-30"></div>
            
            <div className="relative w-full h-full flex items-center justify-center">
              <div className="text-center space-y-6">
                <div className="space-y-3">
                  <div className="flex justify-center gap-3">
                    <div className="w-16 h-16 bg-blue-600 rounded-lg flex items-center justify-center text-2xl border-2 border-blue-400">🧠</div>
                    <div className="w-16 h-16 bg-cyan-600 rounded-lg flex items-center justify-center text-2xl border-2 border-cyan-400">☁️</div>
                    <div className="w-16 h-16 bg-blue-500 rounded-lg flex items-center justify-center text-2xl border-2 border-blue-300">🏗️</div>
                  </div>
                </div>
                <div className="text-sm font-semibold text-slate-600">IA Generativa + Cloud + Full Stack</div>
                <div className="pt-4 border-t border-slate-200">
                  <p className="text-2xl font-bold text-slate-900">End-to-End Solutions</p>
                  <p className="text-xs text-slate-500 mt-2">Enterprise Grade • Production Ready</p>
                </div>
              </div>
            </div>
          </div>
        </div>
      </section>

      {/* Core Pillars */}
      <section className="relative max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 py-20 bg-slate-50 rounded-3xl">
        <h2 className="text-4xl font-bold text-center mb-16">Pilares de Expertise</h2>
        
        <div className="grid grid-cols-1 md:grid-cols-2 gap-8">
          {corePillars.map((pillar, i) => {
            const Icon = pillar.icon;
            return (
              <div 
                key={i}
                className="group bg-white border border-slate-200 rounded-2xl p-8 hover:border-blue-300 hover:shadow-lg transition-all cursor-pointer"
                onClick={() => setExpandedSection(expandedSection === i ? null : i)}
              >
                <div className="flex items-start justify-between mb-4">
                  <div className="flex items-start gap-4">
                    <div className="w-12 h-12 bg-blue-50 rounded-lg flex items-center justify-center">
                      <Icon className="w-6 h-6 text-blue-600" />
                    </div>
                    <div>
                      <h3 className="text-xl font-bold text-slate-900">{pillar.title}</h3>
                      <p className="text-sm text-slate-500 mt-1">{pillar.desc}</p>
                    </div>
                  </div>
                  <ChevronDown className={`w-5 h-5 text-slate-400 transition-transform ${expandedSection === i ? 'rotate-180' : ''}`} />
                </div>

                <div className={`overflow-hidden transition-all duration-300 ${expandedSection === i ? 'max-h-48' : 'max-h-0'}`}>
                  <div className="pt-4 border-t border-slate-100">
                    <div className="flex flex-wrap gap-2">
                      {pillar.items.map((item, j) => (
                        <span key={j} className="px-3 py-1 bg-blue-50 text-blue-700 text-xs font-semibold rounded-full border border-blue-200">
                          {item}
                        </span>
                      ))}
                    </div>
                  </div>
                </div>
              </div>
            );
          })}
        </div>
      </section>

      {/* Impact Metrics */}
      <section className="relative max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 py-20">
        <h2 className="text-4xl font-bold text-center mb-4">Impacto Arquitetural Comprovado</h2>
        <p className="text-center text-slate-600 mb-16">Métricas reais de projetos entregues</p>

        <div className="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-4 gap-6">
          {impactMetrics.map((metric, i) => {
            const Icon = metric.icon;
            return (
              <div key={i} className="bg-gradient-to-br ${metric.color} opacity-5 rounded-2xl border border-slate-200 p-8 group hover:border-slate-300 transition">
                <div className="w-12 h-12 bg-gradient-to-br from-blue-600 to-cyan-600 text-white rounded-lg flex items-center justify-center mb-4">
                  <Icon className="w-6 h-6" />
                </div>
                <div className="text-3xl font-bold text-slate-900">{metric.value}</div>
                <div className="text-sm font-semibold text-slate-700 mt-2">{metric.label}</div>
                <div className="text-xs text-slate-500 mt-2">{metric.desc}</div>
              </div>
            );
          })}
        </div>
      </section>

      {/* Projects */}
      <section className="relative max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 py-20">
        <h2 className="text-4xl font-bold text-center mb-16">Soluções End-to-End Entregues</h2>

        <div className="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-6">
          {projects.map((project, i) => (
            <div
              key={i}
              className="group bg-white border border-slate-200 rounded-2xl p-6 hover:border-blue-300 hover:shadow-lg transition-all"
              onMouseEnter={() => setHoveredProject(i)}
              onMouseLeave={() => setHoveredProject(null)}
            >
              <div className="mb-4">
                <h3 className="text-lg font-bold text-slate-900 group-hover:text-blue-600 transition mb-2">
                  {project.title}
                </h3>
                <p className="text-sm text-slate-600">{project.desc}</p>
              </div>

              <div className="mb-4 pb-4 border-t border-slate-100">
                <p className="text-xs font-semibold text-green-700 bg-green-50 px-3 py-2 rounded-lg inline-block">
                  ✓ {project.impact}
                </p>
              </div>

              <div className="space-y-3">
                <div className="flex flex-wrap gap-2">
                  {project.architecture.map((tech, j) => (
                    <span key={j} className="text-xs bg-slate-100 text-slate-700 px-2.5 py-1 rounded-full font-medium">
                      {tech}
                    </span>
                  ))}
                </div>

                <div className="grid grid-cols-3 gap-2 pt-3 border-t border-slate-100">
                  {Object.entries(project.metrics).map(([key, value]) => (
                    <div key={key} className="text-center">
                      <div className="text-sm font-bold text-blue-600">{value}</div>
                      <div className="text-xs text-slate-500 capitalize">{key}</div>
                    </div>
                  ))}
                </div>
              </div>
            </div>
          ))}
        </div>
      </section>

      {/* Tech Stack */}
      <section className="relative max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 py-20 bg-slate-50 rounded-3xl">
        <h2 className="text-4xl font-bold text-center mb-16">Stack Técnico Completo</h2>

        <div className="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-4 gap-6">
          {Object.entries(techStack).map(([category, techs]) => (
            <div key={category} className="bg-white border border-slate-200 rounded-xl p-6">
              <h3 className="text-sm font-bold text-blue-600 uppercase tracking-wide mb-4">
                {category.replace(/([A-Z])/g, ' $1').trim()}
              </h3>
              <div className="flex flex-wrap gap-2">
                {techs.map((tech, i) => (
                  <span key={i} className="px-3 py-1 bg-blue-50 text-slate-700 text-xs font-medium rounded-full border border-blue-200">
                    {tech}
                  </span>
                ))}
              </div>
            </div>
          ))}
        </div>
      </section>

      {/* Expertise Levels */}
      <section className="relative max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 py-20">
        <h2 className="text-4xl font-bold text-center mb-16">Domínio Técnico</h2>

        <div className="space-y-6 max-w-3xl mx-auto">
          {coreExpertise.map((skill, i) => (
            <div key={i} className="space-y-2">
              <div className="flex items-center justify-between">
                <span className="font-semibold text-slate-900">{skill.name}</span>
                <span className="text-sm font-bold text-blue-600">{skill.level}%</span>
              </div>
              <div className="w-full h-2 bg-slate-200 rounded-full overflow-hidden">
                <div
                  className={`h-full bg-gradient-to-r ${skill.color} transition-all duration-500`}
                  style={{ width: `${skill.level}%` }}
                ></div>
              </div>
            </div>
          ))}
        </div>
      </section>

      {/* CTA */}
      <section className="relative max-w-4xl mx-auto px-4 sm:px-6 lg:px-8 py-20">
        <div className="bg-gradient-to-r from-blue-600 to-cyan-600 rounded-3xl p-12 text-white text-center">
          <h2 className="text-4xl font-bold mb-4">Transforme Seus Processos com IA e Arquitetura</h2>
          <p className="text-lg text-blue-50 mb-8 max-w-2xl mx-auto">
            Especialista em criar soluções corporativas inteligentes que combinam IA Generativa, cloud e engenharia full stack para impacto real.
          </p>

          <div className="flex gap-4 justify-center flex-wrap">
            <button className="px-8 py-3 bg-white text-blue-600 rounded-lg font-semibold hover:bg-blue-50 transition">
              Agendar Consulta
            </button>
            <button className="px-8 py-3 bg-white/20 text-white rounded-lg font-semibold border border-white hover:bg-white/30 transition">
              Ver Documentação
            </button>
          </div>
        </div>
      </section>

      {/* Footer */}
      <footer className="relative max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 py-16 border-t border-slate-200 text-center">
        <div className="space-y-4">
          <p className="text-slate-600">
            © 2024 Leonardo Nogueira • Architect • Full Stack Senior • IA Specialist
          </p>
          <div className="flex justify-center gap-6">
            <a href="#" className="text-slate-600 hover:text-blue-600 transition text-sm font-medium">GitHub</a>
            <a href="#" className="text-slate-600 hover:text-blue-600 transition text-sm font-medium">LinkedIn</a>
            <a href="#" className="text-slate-600 hover:text-blue-600 transition text-sm font-medium">Email</a>
          </div>
        </div>
      </footer>

      <style>{`
        @keyframes gradient-shift {
          0%, 100% { background-position: 0% 50%; }
          50% { background-position: 100% 50%; }
        }

        .animate-gradient {
          background-size: 200% 200%;
          animation: gradient-shift 3s ease infinite;
        }
      `}</style>
    </div>
  );
}
