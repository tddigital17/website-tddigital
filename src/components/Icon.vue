<script setup>
import { computed } from 'vue'
import {
  ArrowRight,
  Briefcase,
  Check,
  CheckCircle,
  ChevronDown,
  ChevronLeft,
  ChevronRight,
  CircleHelp,
  Code2,
  Compass,
  Eye,
  Facebook,
  Fingerprint,
  FolderOpen,
  Github,
  Globe,
  Headphones,
  HeartPulse,
  Info,
  Instagram,
  Landmark,
  Linkedin,
  Mail,
  MapPin,
  Menu,
  MessageCircle,
  Play,
  PlayCircle,
  School,
  Send,
  ShoppingBag,
  Smartphone,
  Sparkles,
  Star,
  Target,
  Twitter,
  Users,
  Video,
  Vote,
  X,
  Youtube,
  Loader2,
} from 'lucide-vue-next'

const icons = {
  arrowRight: ArrowRight,
  briefcase: Briefcase,
  check: Check,
  checkCircle: CheckCircle,
  chevronDown: ChevronDown,
  chevronLeft: ChevronLeft,
  chevronRight: ChevronRight,
  circleHelp: CircleHelp,
  code2: Code2,
  compass: Compass,
  eye: Eye,
  facebook: Facebook,
  fingerprint: Fingerprint,
  folderOpen: FolderOpen,
  github: Github,
  globe: Globe,
  headphones: Headphones,
  heartPulse: HeartPulse,
  info: Info,
  instagram: Instagram,
  landmark: Landmark,
  linkedin: Linkedin,
  loader2: Loader2,
  mail: Mail,
  mapPin: MapPin,
  menu: Menu,
  messageCircle: MessageCircle,
  play: Play,
  playCircle: PlayCircle,
  school: School,
  send: Send,
  shoppingBag: ShoppingBag,
  smartphone: Smartphone,
  sparkles: Sparkles,
  star: Star,
  target: Target,
  twitter: Twitter,
  users: Users,
  video: Video,
  vote: Vote,
  x: X,
  youtube: Youtube,
}

const props = defineProps({
  name: {
    type: String,
    required: true,
  },
})

const icon = computed(() => {
  const componentName = props.name
    .split('-')
    .map((part) => part.charAt(0).toUpperCase() + part.slice(1))
    .join('')
  const key = componentName.charAt(0).toLowerCase() + componentName.slice(1)
  return icons[key] || CircleHelp
})
</script>

<template>
  <component :is="icon" aria-hidden="true" />
</template>
