<script setup lang="ts">
interface ZurieInfoProps {
	compact?: boolean;
}

withDefaults(defineProps<ZurieInfoProps>(), {
	compact: false,
});
</script>

<template>
	<section class="py-8 my-8 border-t border-b border-gray-300 dark:border-gray-700">
		<div class="space-y-6">
			<div class="flex items-center gap-3">
				<Icon name="material-symbols:rocket-launch" class="w-8 h-8 text-primary" />
				<TypographyTitle>ZURIE Studio Tech Dakar</TypographyTitle>
			</div>
			
			<div v-if="!compact" class="space-y-4">
				<TypographyHeadline 
					content="<p>Studio tech d'élite basé à Dakar, spécialisé en développement logiciel, design premium et intelligence artificielle</p>" 
				/>
				
				<div class="grid gap-4 md:grid-cols-2 lg:grid-cols-3">
					<div class="p-4 rounded-lg bg-gray-50 dark:bg-gray-800">
						<div class="flex items-center gap-2 mb-2">
							<Icon name="material-symbols:palette" class="w-5 h-5 text-primary" />
							<h3 class="font-bold">Design Premium</h3>
						</div>
						<p class="text-sm text-gray-600 dark:text-gray-400">Interfaces d'exception pour marques de prestige</p>
					</div>
					
					<div class="p-4 rounded-lg bg-gray-50 dark:bg-gray-800">
						<div class="flex items-center gap-2 mb-2">
							<Icon name="material-symbols:code" class="w-5 h-5 text-primary" />
							<h3 class="font-bold">Développement Logiciel</h3>
						</div>
						<p class="text-sm text-gray-600 dark:text-gray-400">Architectures robustes et scalables</p>
					</div>
					
					<div class="p-4 rounded-lg bg-gray-50 dark:bg-gray-800">
						<div class="flex items-center gap-2 mb-2">
							<Icon name="material-symbols:psychology" class="w-5 h-5 text-primary" />
							<h3 class="font-bold">Intelligence Artificielle</h3>
						</div>
						<p class="text-sm text-gray-600 dark:text-gray-400">Intégration IA native (Google Gemini)</p>
					</div>
					
					<div class="p-4 rounded-lg bg-gray-50 dark:bg-gray-800">
						<div class="flex items-center gap-2 mb-2">
							<Icon name="material-symbols:cloud" class="w-5 h-5 text-primary" />
							<h3 class="font-bold">Infrastructure Cloud</h3>
						</div>
						<p class="text-sm text-gray-600 dark:text-gray-400">Déploiement et maintenance sur AWS, GCP, Azure</p>
					</div>
					
					<div class="p-4 rounded-lg bg-gray-50 dark:bg-gray-800">
						<div class="flex items-center gap-2 mb-2">
							<Icon name="material-symbols:security" class="w-5 h-5 text-primary" />
							<h3 class="font-bold">Sécurité Maximale</h3>
						</div>
						<p class="text-sm text-gray-600 dark:text-gray-400">Protection contre toutes les attaques courantes</p>
					</div>
					
					<div class="p-4 rounded-lg bg-gray-50 dark:bg-gray-800">
						<div class="flex items-center gap-2 mb-2">
							<Icon name="material-symbols:speed" class="w-5 h-5 text-primary" />
							<h3 class="font-bold">Performance Optimisée</h3>
						</div>
						<p class="text-sm text-gray-600 dark:text-gray-400">Lazy loading, code splitting, images optimisées</p>
					</div>
				</div>
				
				<div class="p-6 rounded-lg bg-primary/10 dark:bg-primary/20">
					<h3 class="mb-3 font-bold text-lg">🛡️ Sécurité Maximum</h3>
					<ul class="space-y-2 text-sm">
						<li class="flex items-center gap-2">
							<Icon name="material-symbols:check-circle" class="w-5 h-5 text-green-500" />
							Headers OWASP (CSP stricte, HSTS, X-Frame-Options)
						</li>
						<li class="flex items-center gap-2">
							<Icon name="material-symbols:check-circle" class="w-5 h-5 text-green-500" />
							Protection CSRF avec tokens sécurisés
						</li>
						<li class="flex items-center gap-2">
							<Icon name="material-symbols:check-circle" class="w-5 h-5 text-green-500" />
							Rate Limiting (global, fingerprinting, circuit breaker)
						</li>
						<li class="flex items-center gap-2">
							<Icon name="material-symbols:check-circle" class="w-5 h-5 text-green-500" />
							Anti-Bot (détection WebDriver, headless, plugins)
						</li>
						<li class="flex items-center gap-2">
							<Icon name="material-symbols:check-circle" class="w-5 h-5 text-green-500" />
							Probabilité d'attaque réussie : <strong>&lt; 5-8%</strong>
						</li>
					</ul>
				</div>
				
				<div class="grid gap-4 md:grid-cols-2">
					<div class="p-4 rounded-lg border border-gray-300 dark:border-gray-700">
						<h3 class="mb-2 font-bold">📊 SEO Optimisé</h3>
						<ul class="space-y-1 text-sm text-gray-600 dark:text-gray-400">
							<li>• Meta Tags Dynamiques</li>
							<li>• Schema.org (Organization, LocalBusiness)</li>
							<li>• Sitemap Dynamique</li>
							<li>• Local SEO optimisé</li>
						</ul>
					</div>
					
					<div class="p-4 rounded-lg border border-gray-300 dark:border-gray-700">
						<h3 class="mb-2 font-bold">🚀 Performance</h3>
						<ul class="space-y-1 text-sm text-gray-600 dark:text-gray-400">
							<li>• Lazy Loading des routes</li>
							<li>• Code Splitting automatique</li>
							<li>• Images WebP optimisées</li>
							<li>• Core Web Vitals optimisés</li>
						</ul>
					</div>
				</div>
			</div>
			
			<div v-else class="space-y-2">
				<p class="text-sm text-gray-600 dark:text-gray-400">
					Studio tech d'élite basé à Dakar, spécialisé en développement logiciel, design premium et intelligence artificielle.
				</p>
				<div class="flex flex-wrap gap-2">
					<UBadge color="primary" variant="subtle">Design Premium</UBadge>
					<UBadge color="primary" variant="subtle">IA Native</UBadge>
					<UBadge color="primary" variant="subtle">Sécurité Maximum</UBadge>
					<UBadge color="primary" variant="subtle">Performance Optimisée</UBadge>
				</div>
			</div>
			
			<div class="flex items-center gap-4 pt-4 border-t border-gray-300 dark:border-gray-700">
				<a 
					href="https://zurie.fr" 
					target="_blank" 
					rel="noopener noreferrer"
					class="flex items-center gap-2 text-sm font-medium text-primary hover:underline"
				>
					<Icon name="material-symbols:link" class="w-4 h-4" />
					Visiter le site ZURIE
				</a>
				<a 
					href="mailto:infos@zurie.fr" 
					class="flex items-center gap-2 text-sm font-medium text-primary hover:underline"
				>
					<Icon name="material-symbols:mail" class="w-4 h-4" />
					infos@zurie.fr
				</a>
				<span class="text-sm text-gray-500 dark:text-gray-400">
					Plateau, Dakar, Sénégal
				</span>
			</div>
		</div>
	</section>
</template>
