<script setup lang="ts">
import { Head } from '@inertiajs/vue3';
import {profile, experience, skills, projects} from '@/pages/data';
</script>

<template>
    <Head title="Eyob Alebachew | Portfolio" />

    <div class="min-h-screen bg-slate-950 text-slate-100">
        <main class="mx-auto flex max-w-6xl flex-col gap-8 px-6 py-10 lg:px-8">
            <section class="rounded-3xl border border-slate-800 bg-slate-900/80 p-8 shadow-2xl shadow-black/20">
                <div class="flex flex-col gap-6 lg:flex-row lg:items-end lg:justify-between">
                    <div class="max-w-2xl">
                        <p class="mb-3 text-sm uppercase tracking-[0.3em] text-cyan-400">
                            Portfolio
                        </p>
                        <h1 class="text-4xl font-semibold sm:text-5xl">
                            {{ profile.name }}
                        </h1>
                        <p class="mt-3 text-lg text-slate-300">
                            {{ profile.title }}
                        </p>
                        <p class="mt-6 text-base leading-7 text-slate-400">
                            {{ profile.summary }}
                        </p>
                    </div>

                    <div class="rounded-2xl border border-slate-800 bg-slate-950/70 p-5 text-sm text-slate-300">
                        <p>📍 {{ profile.location }}</p>
                        <p>📞 {{ profile.phone }}</p>
                        <p>✉ {{ profile.email }}</p>
                        <a
                            href="https://github.com/Eyueth"
                            target="_blank"
                            rel="noreferrer"
                            class="mt-3 inline-block font-medium text-cyan-400 hover:text-cyan-300"
                        >
                            GitHub: {{ profile.github }}
                        </a>
                    </div>
                </div>
            </section>

            <section class="grid gap-8 lg:grid-cols-[1.2fr_0.8fr]">
                <div class="rounded-3xl border border-slate-800 bg-slate-900/70 p-8">
                    <h2 class="text-2xl font-semibold">Experience</h2>
                    <div class="mt-6 space-y-6">
                        <div
                            v-for="item in experience"
                            :key="item.company"
                            class="rounded-2xl border border-slate-800 bg-slate-950/70 p-5"
                        >
                            <div class="flex flex-col gap-1 sm:flex-row sm:items-center sm:justify-between">
                                <div>
                                    <h3 class="font-semibold text-white">
                                        {{ item.role }}
                                    </h3>
                                    <p class="text-cyan-400">{{ item.company }}</p>
                                </div>
                                <p class="text-sm text-slate-400">{{ item.period }}</p>
                            </div>
                            <ul class="mt-3 list-disc space-y-2 pl-5 text-sm text-slate-400">
                                <li v-for="detail in item.details" :key="detail">
                                    {{ detail }}
                                </li>
                            </ul>
                        </div>
                    </div>
                </div>

                <div class="rounded-3xl border border-slate-800 bg-slate-900/70 p-8">
                    <h2 class="text-2xl font-semibold">Skills</h2>
                    <div class="mt-6 flex flex-wrap gap-3">
                        <span
                            v-for="skill in skills"
                            :key="skill"
                            class="rounded-full border border-slate-700 bg-slate-950 px-3 py-2 text-sm text-slate-300"
                        >
                            {{ skill }}
                        </span>
                    </div>

                    <div class="mt-8 rounded-2xl border border-slate-800 bg-slate-950/70 p-5">
                        <h3 class="font-semibold text-white">Education</h3>
                        <p class="mt-2 text-slate-300">
                            Bachelor of Science in Computer Science
                        </p>
                        <p class="text-sm text-slate-400">Bahir Dar University</p>
                        <p class="mt-2 text-sm text-cyan-400">CGPA: 3.70/4.00</p>
                    </div>
                </div>
            </section>

            <section class="rounded-3xl border border-slate-800 bg-slate-900/70 p-8">
                <h2 class="text-2xl font-semibold">Projects</h2>
                <div class="mt-6 grid gap-6 lg:grid-cols-3">
                    <article
                        v-for="project in projects"
                        :key="project.name"
                        class="rounded-2xl border border-slate-800 bg-slate-950/70 p-5"
                    >
                        <h3 class="font-semibold text-white">{{ project.name }}</h3>
                        <p class="mt-2 text-sm text-cyan-400">{{ project.stack }}</p>
                        <p class="mt-3 text-sm leading-6 text-slate-400">
                            {{ project.description }}
                        </p>
                    </article>
                </div>
            </section>
        </main>
    </div>
</template>
              
