FROM php:8.3-fpm-alpine
# 替换为国内镜像源
RUN echo "https://mirrors.aliyun.com/alpine/v3.21/main" > /etc/apk/repositories && \
    echo "https://mirrors.aliyun.com/alpine/v3.21/community" >> /etc/apk/repositories

# 安装依赖并配置 PHP 扩展
RUN apk update && apk add --no-cache \
    # 安装依赖
    libpng \
    libjpeg-turbo \
    freetype \
    libwebp \
    libzip \
    zlib \
    curl \
    libpng-dev \
    libjpeg-turbo-dev \
    freetype-dev \
    libwebp-dev \
    libzip-dev \
    zlib-dev \
    oniguruma-dev \
    libxml2-dev \
    curl-dev \
    bash \
    # 安装PHP 扩展	
    && docker-php-ext-configure gd --with-jpeg --with-freetype --with-webp \
    && docker-php-ext-install \
        pdo \
        pdo_mysql \
        mysqli \
        gd \
        zip \
        opcache \
        bcmath \
    # 删除编译时依赖
    # 删除编译时依赖
    && apk del \
        libpng-dev \
        libjpeg-turbo-dev \
        freetype-dev \
        libwebp-dev \
        libzip-dev \
        zlib-dev \
        oniguruma-dev \
        libxml2-dev \
        curl-dev \
    && rm -rf /var/cache/apk/*

#COPY entrypoint.sh /usr/local/bin/entrypoint.sh
#RUN chmod +x /usr/local/bin/entrypoint.sh
#ENTRYPOINT ["/usr/local/bin/entrypoint.sh"]