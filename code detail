/**
 * @license
 * SPDX-License-Identifier: Apache-2.0
 */

import React, { useState, useEffect } from 'react';
import { motion, AnimatePresence } from 'motion/react';
import { 
  ChevronDown, 
  TrendingUp, 
  Users, 
  Video, 
  Target, 
  Zap, 
  Award, 
  ArrowRight,
  BarChart3,
  Globe,
  Camera,
  Layers,
  Lightbulb,
  Puzzle
} from 'lucide-react';

const slides = [
  {
    id: 'hero',
    type: 'hero',
    title: 'FY26 Review',
    subtitle: '欣妍｜买家侧营销方向｜2年+经验',
    description: '聚焦头部商家差异化营销场景与平台优质直播/短视频内容建设',
    titleSize: 'text-5xl md:text-8xl',
    subtitleSize: 'text-sm md:text-base'
  },
  {
    id: 'experience',
    type: 'list-v2',
    title: '核心经历',
    titleSize: 'text-3xl md:text-5xl',
    items: [
      { year: '2023.11 – 2024.06', content: '超级星厂牌', subContent: '头部商家营销' },
      { year: '2024.07 – 2025.03', content: '三月大促，线上展会', subContent: '营销活动 / 内容频道' },
      { year: '2025.04 – 2026.03', content: 'Open Day，线上展会', subContent: '头部商家营销 / 内容频道' }
    ]
  },
  {
    id: 'output-summary',
    type: 'modular',
    title: 'FY26 关键工作产出',
    titleSize: 'text-4xl md:text-6xl',
    modules: [
      { title: '头部商家营销方案', desc: '为头部商家提供品牌化、定制化的营销解决方案，直接关联商业化营收。', icon: <Target className="w-6 h-6" /> },
      { title: '大盘商家的内容化', desc: '构建沉浸式内容消费场景，系统沉淀行业内容标准，激活商家内容生产动能。', icon: <Video className="w-6 h-6" /> },
      { title: '补位PD角色', desc: '身兼业务与产品双角色，将营销策略转化为PRD，协调开发、数科团队落地。', icon: <Zap className="w-6 h-6" /> }
    ]
  },
  {
    id: 'open-day-intro',
    type: 'detailed-hero-v2',
    title: '01 | Open Day',
    titleSize: 'text-4xl md:text-6xl',
    subtitle: '为头部商家提供品牌化、定制化的营销解决方案，直接关联商业化营收。',
    image: 'https://intranetproxy.alipay.com/skylark/lark/0/2026/png/122056567/1772774758931-b32bc203-6e2f-4ade-ad8f-47316863d4d1.png?x-oss-process=image%2Fformat%2Cwebp',
    keywords: '买家洞察、设计链路、落地（效率优先）'
  },
  {
    id: 'open-day-detail',
    type: 'detailed-grid',
    title: '01 | Open Day',
    titleSize: 'text-3xl md:text-4xl',
    subtitle: '全链路营销设计与标准化场景沉淀',
    content: [
      {
        label: '场景搭建 — 全链路营销链路设计',
        list: [
          '完成全链路Open Day营销场景设计，涵盖线上展会阵地 + 商家旺铺 + 私域引流 + 沉浸式直播间。',
          '创新试跑 24h工厂直播模式，沉淀中英文视频素材与直播切片等品牌内容资产。',
          '参与商家平均 UV 增长 211%，商机量提升 71%，优质买家（L2+）增长 30%。'
        ]
      },
      {
        label: '内容迭代 — 标准化场景模版沉淀',
        list: [
          'S1：重点打造「探厂直播」标准化内容表达，夯实工厂实力可视化基础。',
          'S2：拓展多元诉求适配场景：1月推出「新品发布会」专场；3月上线「MADE BY YOU 定制专场」。',
          '配套设计通用权益包与大买专属权益体系，沉淀可复用的内容框架与玩法机制。'
        ]
      },
      {
        label: '事件策划与影响力打造 — 强化IP与商业价值',
        list: [
          'S1：联动招商侧，完成14家知名商家策划执行，关联营收 600万元。',
          'S2：完成22家落地，建立月度主题传播节奏，强化Open Day首选地位。',
          '全年累计关联商业化营收达 3400万元，成为平台头部商家首选营销方案。'
        ]
      }
    ]
  },
  {
    id: 'ots-intro',
    type: 'detailed-hero-v2',
    title: '02 | Online Trade Show',
    titleSize: 'text-3xl md:text-5xl',
    subtitle: '打造以直播/短视频为核心的内容营销阵地',
    image: 'https://intranetproxy.alipay.com/skylark/lark/0/2026/png/122056567/1772713288783-9dad80d2-6df5-4458-8994-ff57ee7b987c.png?x-oss-process=image%2Fformat%2Cwebp',
    keywords: '沉浸式体验、内容标准、供给激活'
  },
  {
    id: 'ots-detail',
    type: 'detailed-grid',
    title: '02 | Online Trade Show',
    titleSize: 'text-3xl md:text-4xl',
    subtitle: '内容消费场景构建与供给侧激活',
    content: [
      {
        label: '产品侧 — 构建沉浸式内容消费场景',
        list: [
          'S1：联动PD及交互团队，完成OTS正式迁入“找工厂”频道作为固定栏目，上线Feeds流+沉浸式体验。',
          'S2：将优质直播/短视频嵌入公域商卡，直播融入“找工厂”场景带来显著增量——英语L0买家AB测试转化率提升 +11.62%。'
        ]
      },
      {
        label: '内容标准与质量 — 打造可复用的内容基建',
        list: [
          'S1：定义五大核心内容模板：探厂、样品间、定制演示、产品测评、展会现场，统一内容表达范式。',
          'S2：完成15大行业专属模版优化，规范直播SOP「内容脚本+转化钩子+AI承接」，优质直播渗透率提升至60%+。'
        ]
      },
      {
        label: '内容供给侧 — 激活商家内容生产动能',
        list: [
          'S1：借势9月大促“商机赛道”，拉动超3000场直播、2.5万+条短视频发布，覆盖5000+优质工厂。',
          'S2：建立商家分层激励机制（冷启/腰部/头部），推动月度直播场次从3000+提升至1万+。'
        ]
      }
    ]
  },
  {
    id: 'growth-reflection',
    type: 'growth-v2',
    title: '二. 个人成长沉淀',
    titleSize: 'text-4xl md:text-6xl',
    subtitle: '从执行到策略，从单点到机制',
    points: [
      {
        title: '01 | 主动洞察',
        desc: '不再止步于理解+执行，而能主动洞察、制定策略。主导多轮买家访谈，反推内容运营链路。',
        icon: <TrendingUp className="w-6 h-6" />
      },
      {
        title: '02 | 构建机制',
        desc: '拒绝单点爆破。升级直播商家分层滚动激励机制；沉淀“开箱即用”的内容工具箱。',
        icon: <Layers className="w-6 h-6" />
      },
      {
        title: '03 | 主动牵头与协调',
        desc: '身兼业务与产品双角色，将营销策略转化为PRD，协调开发、数科团队落地。',
        icon: <Users className="w-6 h-6" />
      },
      {
        title: '04 | 仍有遗憾',
        desc: 'Open Day 没有做出一个人尽皆知的big case，对Big Case的构建、提前筹备与放声仍需加强方法论沉淀。',
        icon: <Puzzle className="w-6 h-6" />
      }
    ]
  },
  {
    id: 'okr-ots',
    type: 'detailed',
    title: '三. FY27 S1 OKR',
    titleSize: 'text-3xl md:text-5xl',
    subtitle: 'Online Trade Show',
    content: [
      {
        label: '思考先行',
        text: '对于平台工厂类商家，品商信息可罗列卖点，AI工具/Accio可提炼信息，但无法承载 1v1实时问答的服务性、工艺产能眼见为实的信任感、动态展现产品使用&定制样式的直观性，因此围绕品商实力的专业直播&视频内容依然具有不可替代性。'
      },
      {
        label: '核心动作',
        list: [
          '定义直播价值场景（区分行业），包括快消品上新、机械品1v1洽谈等。',
          '最大化商家供给：建立分层激励机制与产品化教育机制。',
          '实现优质内容分发：覆盖全语种买家，解决多语言问题。',
          '短视频单独探索：研究吸引性内容（新品、工艺、案例）的有效分发链路。'
        ]
      }
    ]
  },
  {
    id: 'okr-open-day',
    type: 'detailed',
    title: '三. FY27 S1 OKR',
    titleSize: 'text-3xl md:text-5xl',
    subtitle: 'Open Day',
    content: [
      {
        label: '思考先行',
        text: '对于头部商家，差异化的品牌展现是必要需求，希望以独特的方式被更多看见、被记住、被换来长远更大的转化。因此，以长期服务追踪为导向，跨越一个月的活动周期，设计头部商家可长期follow的品牌成长路径是有价值的事情。'
      },
      {
        label: '核心动作',
        list: [
          '拓展多种内容化展现实力的场景模版，联动Agency解决规模化运营承接。',
          '大型事件策划与打造：跨团队合作（如美国大买、CoCreate US）。',
          'Open Day商家成长路径指南：涵盖冷启动至成熟期的全周期运营指南。'
        ]
      }
    ]
  },
  {
    id: 'personal-plan',
    type: 'split-plan-v2',
    title: '四. 个人发展计划',
    titleSize: 'text-4xl md:text-6xl',
    plans: [
      {
        label: '专业深耕',
        desc: '持续以买家侧营销为主要发展方向，围绕品效合一的营销活动、直播&短视频内容域规模运营更为深入，并形成个人的方法&影响力。',
        icon: <Target className="w-8 h-8" />
      },
      {
        label: '能力提升',
        desc: '积极参与平台级市场战役，提升市场部核心能力-传播创意、品牌叙事能力。',
        icon: <TrendingUp className="w-8 h-8" />
      }
    ],
    isLast: true
  }
];

export default function App() {
  const [activeSlide, setActiveSlide] = useState(0);

  const handleScroll = (e: React.UIEvent<HTMLDivElement>) => {
    const scrollPos = e.currentTarget.scrollTop;
    const height = window.innerHeight;
    const index = Math.round(scrollPos / height);
    if (index !== activeSlide) {
      setActiveSlide(index);
    }
  };

  const containerVariants = {
    hidden: { opacity: 0 },
    visible: {
      opacity: 1,
      transition: {
        staggerChildren: 0.1,
        delayChildren: 0.2,
      },
    },
  };

  const itemVariants = {
    hidden: { opacity: 0, y: 20 },
    visible: {
      opacity: 1,
      y: 0,
      transition: {
        duration: 0.8,
        ease: [0.16, 1, 0.3, 1], // Custom ease-out cubic
      },
    },
  };

  return (
    <div className="slide-container" onScroll={handleScroll}>
      {slides.map((slide, index) => (
        <section key={slide.id} className="slide">
          <div className="bg-glow top-[-20%] left-[-10%]" />
          <div className="bg-glow bottom-[-20%] right-[-10%]" />
          
          <AnimatePresence mode="wait">
            {activeSlide === index && (
              <motion.div
                variants={containerVariants}
                initial="hidden"
                animate="visible"
                exit="hidden"
                className="max-w-7xl w-full text-center px-4 z-10"
              >
                {slide.type === 'hero' && (
                  <div className="flex flex-col items-center">
                    <motion.div variants={itemVariants} className="micro-label mb-6">Annual Performance Review</motion.div>
                    <motion.h1 
                      variants={itemVariants}
                      className={`${slide.titleSize || 'text-7xl md:text-9xl'} font-display font-bold tracking-tightest mb-8 text-gradient`}
                    >
                      {slide.title}
                    </motion.h1>
                    <motion.div variants={itemVariants} className="h-px w-24 bg-gold/30 mb-8" />
                    <motion.p 
                      variants={itemVariants}
                      className={`${slide.subtitleSize || 'text-sm md:text-base'} text-silver font-medium mb-10 tracking-[0.2em] uppercase`}
                    >
                      {slide.subtitle}
                    </motion.p>
                    <motion.p 
                      variants={itemVariants}
                      className="text-lg md:text-xl max-w-3xl mx-auto text-white/70 mb-12 leading-relaxed font-light"
                    >
                      {slide.description}
                    </motion.p>
                  </div>
                )}

                {slide.type === 'list-v2' && (
                  <div className="text-left max-w-5xl mx-auto">
                    <motion.div variants={itemVariants} className="micro-label mb-4">Professional Journey</motion.div>
                    <motion.h2 variants={itemVariants} className={`${slide.titleSize || 'text-6xl'} font-display font-bold mb-20 text-gradient tracking-tightest`}>{slide.title}</motion.h2>
                    <div className="space-y-12 relative">
                      <div className="absolute left-[2.1rem] top-0 bottom-0 w-px bg-white/5" />
                      {slide.items?.map((item, i) => (
                        <motion.div key={i} variants={itemVariants} className="grid grid-cols-12 gap-8 items-start group relative">
                          <div className="col-span-5 flex items-center gap-6">
                            <div className="w-2 h-2 rounded-full bg-gold/40 group-hover:bg-gold transition-colors z-10" />
                            <div className="text-2xl font-mono text-white/40 group-hover:text-white transition-colors">
                              {item.year}
                            </div>
                          </div>
                          <div className="col-span-7">
                            <h3 className="text-2xl font-medium text-white/80 leading-relaxed group-hover:text-white transition-all duration-500">
                              {item.content}
                            </h3>
                            {item.subContent && (
                              <p className="text-lg text-white/30 font-light mt-1">{item.subContent}</p>
                            )}
                          </div>
                        </motion.div>
                      ))}
                    </div>
                  </div>
                )}

                {slide.type === 'modular' && (
                  <div className="text-center max-w-7xl mx-auto">
                    <motion.div variants={itemVariants} className="mb-20">
                      <div className="micro-label mb-4">Key Achievements</div>
                      <h2 className={`${slide.titleSize || 'text-7xl'} font-display font-bold mb-6 text-gradient tracking-tightest`}>{slide.title}</h2>
                    </motion.div>
                    <div className="grid md:grid-cols-3 gap-8">
                      {slide.modules?.map((mod, i) => (
                        <motion.div 
                          key={i} 
                          variants={itemVariants}
                          className="glass card-vibrant p-10 rounded-[2.5rem] text-left group"
                        >
                          <div className="flex items-center gap-4 mb-8">
                            <div className="w-12 h-12 rounded-xl bg-white/5 flex items-center justify-center group-hover:bg-gold/10 transition-all duration-500">
                              {React.cloneElement(mod.icon as React.ReactElement, { className: "w-6 h-6 text-white/40 group-hover:text-gold transition-colors" })}
                            </div>
                            <h3 className="text-xl font-bold tracking-tight group-hover:text-white transition-colors">{mod.title}</h3>
                          </div>
                          <p className="text-white/40 leading-relaxed text-base font-light group-hover:text-white/60 transition-colors">{mod.desc}</p>
                        </motion.div>
                      ))}
                    </div>
                  </div>
                )}

                {slide.type === 'detailed-hero-v2' && (
                  <div className="grid md:grid-cols-2 gap-16 items-center text-left max-w-7xl mx-auto">
                    <div className="space-y-8">
                      <motion.div variants={itemVariants}>
                        <h2 className={`${slide.titleSize || 'text-7xl'} font-display font-bold mb-4 text-gradient tracking-tightest`}>{slide.title}</h2>
                        <p className="text-2xl text-white/40 font-light leading-relaxed mb-8">{slide.subtitle}</p>
                      </motion.div>
                      <motion.div variants={itemVariants} className="flex flex-wrap gap-3">
                        {slide.keywords?.split('、').map((kw, k) => (
                          <span key={k} className="px-4 py-2 rounded-full glass micro-label text-[0.6rem] border-white/5">{kw}</span>
                        ))}
                      </motion.div>
                    </div>
                    <motion.div 
                      variants={itemVariants}
                      className="rounded-[3rem] overflow-hidden glass p-4 shadow-2xl relative group h-[60vh]"
                    >
                      <img 
                        src={slide.image} 
                        alt={slide.title} 
                        className="w-full h-full object-cover rounded-[2.5rem] transition-all duration-1000"
                        referrerPolicy="no-referrer"
                      />
                    </motion.div>
                  </div>
                )}

                {slide.type === 'detailed-grid' && (
                  <div className="text-left max-w-7xl mx-auto">
                    <div className="grid grid-cols-12 gap-12">
                      <div className="col-span-12 mb-8">
                        <motion.div variants={itemVariants}>
                          <h2 className={`${slide.titleSize || 'text-6xl'} font-display font-bold mb-4 text-gradient tracking-tightest`}>{slide.title}</h2>
                          <p className="text-2xl text-white/40 font-light leading-relaxed">{slide.subtitle}</p>
                        </motion.div>
                      </div>
                      <div className="col-span-12 md:col-span-4">
                        {slide.content?.[0] && (
                          <motion.div variants={itemVariants} className="glass p-8 rounded-[2rem] border-white/5 h-full">
                            <h3 className="text-lg font-bold text-white mb-6 bg-slate-800/60 px-4 py-3 rounded-xl inline-block border border-slate-700/50 shadow-xl">
                              {slide.content[0].label}
                            </h3>
                            <ul className="space-y-4">
                              {slide.content[0].list?.map((li, j) => (
                                <li key={j} className="flex items-start gap-4 group">
                                  <div className="w-1.5 h-1.5 rounded-full bg-gold/40 group-hover:bg-gold transition-colors mt-2 shrink-0" />
                                  <span className="text-white/50 group-hover:text-white/80 transition-colors font-light text-sm leading-relaxed">{li}</span>
                                </li>
                              ))}
                            </ul>
                          </motion.div>
                        )}
                      </div>
                      <div className="col-span-12 md:col-span-4">
                        {slide.content?.[1] && (
                          <motion.div variants={itemVariants} className="glass p-8 rounded-[2rem] border-white/5 h-full">
                            <h3 className="text-lg font-bold text-white mb-6 bg-slate-800/60 px-4 py-3 rounded-xl inline-block border border-slate-700/50 shadow-xl">
                              {slide.content[1].label}
                            </h3>
                            <ul className="space-y-4">
                              {slide.content[1].list?.map((li, j) => (
                                <li key={j} className="flex items-start gap-4 group">
                                  <div className="w-1.5 h-1.5 rounded-full bg-gold/40 group-hover:bg-gold transition-colors mt-2 shrink-0" />
                                  <span className="text-white/50 group-hover:text-white/80 transition-colors font-light text-sm leading-relaxed">{li}</span>
                                </li>
                              ))}
                            </ul>
                          </motion.div>
                        )}
                      </div>
                      <div className="col-span-12 md:col-span-4">
                        {slide.content?.[2] && (
                          <motion.div variants={itemVariants} className="glass p-8 rounded-[2rem] border-white/5 h-full">
                            <h3 className="text-lg font-bold text-white mb-6 bg-slate-800/60 px-4 py-3 rounded-xl inline-block border border-slate-700/50 shadow-xl">
                              {slide.content[2].label}
                            </h3>
                            <ul className="space-y-4">
                              {slide.content[2].list?.map((li, j) => (
                                <li key={j} className="flex items-start gap-4 group">
                                  <div className="w-1.5 h-1.5 rounded-full bg-gold/40 group-hover:bg-gold transition-colors mt-2 shrink-0" />
                                  <span className="text-white/50 group-hover:text-white/80 transition-colors font-light text-sm leading-relaxed">{li}</span>
                                </li>
                              ))}
                            </ul>
                          </motion.div>
                        )}
                      </div>
                    </div>
                  </div>
                )}

                {slide.type === 'detailed' && (
                  <div className="text-left max-w-7xl mx-auto">
                    <div className="grid md:grid-cols-12 gap-16">
                      <div className="md:col-span-4">
                        <motion.div variants={itemVariants} className="sticky top-0">
                          <div className="micro-label mb-4">Future Plan</div>
                          <h2 className={`${slide.titleSize || 'text-6xl'} font-display font-bold mb-2 text-gradient tracking-tightest`}>{slide.title}</h2>
                          <div className="inline-block px-4 py-1 rounded-lg bg-white/5 border border-white/10 mb-12">
                            <p className="text-sm text-white/40 font-light tracking-widest uppercase">{slide.subtitle}</p>
                          </div>
                          <div className="h-px w-full bg-white/5" />
                        </motion.div>
                      </div>
                      <div className="md:col-span-8 space-y-16">
                        {slide.content?.map((item, i) => (
                          <motion.div key={i} variants={itemVariants} className={item.label === '思考先行' ? 'pull-quote' : 'space-y-6'}>
                            <h3 className="micro-label text-gold/60 mb-4">{item.label}</h3>
                            {item.text && <p className="text-white/80 leading-relaxed text-xl font-light">{item.text}</p>}
                            {item.list && (
                              <ul className="space-y-6">
                                {item.list.map((li, j) => (
                                  <li key={j} className="flex items-start gap-6 group">
                                    <div className="w-px h-6 bg-gold/20 group-hover:bg-gold transition-colors mt-1" />
                                    <span className="text-white/50 group-hover:text-white/80 transition-colors font-light leading-relaxed">{li}</span>
                                  </li>
                                ))}
                              </ul>
                            )}
                          </motion.div>
                        ))}
                      </div>
                    </div>
                  </div>
                )}

                {slide.type === 'growth-v2' && (
                  <div className="text-left max-w-7xl mx-auto">
                    <motion.div variants={itemVariants} className="mb-20">
                      <div className="micro-label mb-4">Self Evolution</div>
                      <h2 className={`${slide.titleSize || 'text-7xl'} font-display font-bold mb-6 text-gradient tracking-tightest`}>{slide.title}</h2>
                      <p className="text-xl md:text-2xl text-white/30 font-light tracking-[0.3em] uppercase">{slide.subtitle}</p>
                    </motion.div>
                    <div className="grid md:grid-cols-2 lg:grid-cols-4 gap-6 mb-20">
                      {slide.points?.map((p, i) => (
                        <motion.div 
                          key={i} 
                          variants={itemVariants}
                          className="glass p-8 rounded-[2.5rem] relative overflow-hidden group border-white/5 flex flex-col h-full"
                        >
                          <div className="flex items-center gap-4 mb-6">
                            <div className="w-10 h-10 rounded-xl bg-white/5 flex items-center justify-center group-hover:bg-gold/10 transition-all duration-500 shrink-0">
                              {React.cloneElement(p.icon as React.ReactElement, { className: "w-5 h-5 text-white/30 group-hover:text-gold transition-colors" })}
                            </div>
                            <h3 className="text-lg font-bold tracking-tight group-hover:text-white transition-colors">{p.title}</h3>
                          </div>
                          <p className="text-white/30 leading-relaxed text-sm font-light group-hover:text-white/50 transition-colors">{p.desc}</p>
                        </motion.div>
                      ))}
                    </div>
                  </div>
                )}

                {slide.type === 'split-plan-v2' && (
                  <div className="text-center max-w-6xl mx-auto">
                    <motion.div variants={itemVariants} className="mb-20">
                      <div className="micro-label mb-4">Future Roadmap</div>
                      <h2 className={`${slide.titleSize || 'text-7xl'} font-display font-bold mb-4 text-gradient tracking-tightest`}>{slide.title}</h2>
                    </motion.div>
                    <div className="grid md:grid-cols-2 gap-8">
                      {slide.plans?.map((plan, i) => (
                        <motion.div key={i} variants={itemVariants} className="glass p-16 rounded-[3rem] flex flex-col items-center justify-center text-center group border-white/5">
                          <div className="w-16 h-16 rounded-2xl bg-white/5 flex items-center justify-center mb-8 group-hover:bg-gold/10 transition-all duration-500">
                            {React.cloneElement(plan.icon as React.ReactElement, { className: "w-8 h-8 text-white/30 group-hover:text-gold transition-colors" })}
                          </div>
                          <h3 className="text-3xl font-bold text-gold/80 mb-8 group-hover:text-gold transition-colors">{plan.label}</h3>
                          <p className="text-lg text-white/40 font-light leading-relaxed group-hover:text-white/60 transition-colors">
                            {plan.desc}
                          </p>
                        </motion.div>
                      ))}
                    </div>
                  </div>
                )}
              </motion.div>
            )}
          </AnimatePresence>

          {!slide.isLast && (
            <motion.div 
              className="absolute bottom-12 left-1/2 -translate-x-1/2 text-white/10"
              animate={{ y: [0, 10, 0] }}
              transition={{ repeat: Infinity, duration: 2 }}
            >
              <ChevronDown className="w-8 h-8" />
            </motion.div>
          )}
        </section>
      ))}

      {/* Navigation Dots */}
      <div className="fixed right-12 top-1/2 -translate-y-1/2 space-y-8 z-50">
        {slides.map((_, i) => (
          <div 
            key={i}
            className={`w-px transition-all duration-700 ${activeSlide === i ? 'bg-gold h-12' : 'bg-white/10 h-4'}`}
          />
        ))}
      </div>
    </div>
  );
}
