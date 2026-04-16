<template>
  <footer class="bg-bg-section border-t border-border-light py-8">
    <div class="max-w-6xl mx-auto px-4 sm:px-6">
      <div class="flex flex-col sm:flex-row items-center justify-between gap-4">
        <div class="flex items-center gap-2">
          <div class="w-7 h-7 rounded-lg bg-gradient-to-br from-primary to-accent flex items-center justify-center">
            <svg class="w-4 h-4 text-white" fill="none" stroke="currentColor" viewBox="0 0 24 24">
              <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2"
                d="M4 16v1a3 3 0 003 3h10a3 3 0 003-3v-1m-4-4l-4 4m0 0l-4-4m4 4V4" />
            </svg>
          </div>
          <span class="text-sm font-bold bg-gradient-to-r from-primary to-accent bg-clip-text text-transparent">VideoGrab</span>
        </div>
        <p class="text-xs text-text-muted text-center leading-relaxed">
          本工具仅供学习交流使用，请尊重视频版权，勿用于商业用途。下载内容的版权归原作者所有。
        </p>
        <p class="text-xs text-text-muted">
          &copy; {{ new Date().getFullYear() }} VideoGrab
        </p>
      </div>
    </div>
  </footer>
</template>
